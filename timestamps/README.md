# Proof of date

Each dated folder here holds trusted timestamp proofs for the vault's fingerprint files (`SHA256SUMS`, `MANIFEST.csv`), which in turn list the hash of every document. A proof shows that a file with exactly this content existed no later than the time shown. Only the fingerprint (SHA-256 hash) of each file was ever sent to the timestamp services, never the documents.

Two independent kinds of proof:
- **RFC 3161** (`*.freetsa.tsr`, `*.digicert.tsr`): signed by two separate timestamp authorities, FreeTSA and DigiCert. The `*.tsq` file is the request that was sent.
- **OpenTimestamps** (`*.ots`): anchored to the Bitcoin blockchain. A new proof is "pending" for a few hours, then is upgraded to a Bitcoin block attestation.

The copy of each stamped file in the folder is byte-identical to the one that was stamped; change a single byte and verification fails.

## Verify an RFC 3161 proof

Run inside a dated folder (needs OpenSSL):

```
openssl ts -verify -data SHA256SUMS -in SHA256SUMS.freetsa.tsr -CAfile ca/freetsa-cacert.pem -untrusted ca/freetsa-tsa.crt
openssl ts -reply -in SHA256SUMS.digicert.tsr -token_out -out /tmp/dc.tok
openssl pkcs7 -inform DER -in /tmp/dc.tok -print_certs > /tmp/dc-chain.pem
openssl ts -verify -data SHA256SUMS -in SHA256SUMS.digicert.tsr -CAfile ca/digicert-root.pem -untrusted /tmp/dc-chain.pem
openssl ts -reply -in SHA256SUMS.freetsa.tsr -text
```

`Verification: OK` means the signature is valid and the hash matches. The last command prints the time the authority attested (`Time stamp:`). The CA files in `ca/` are FreeTSA's published certificates (freetsa.org/files/) and DigiCert's Trusted Root G4 (also in common system trust stores, so `-CAfile /etc/ssl/cert.pem` works too). `ca/digicert-chain.pem` is the intermediate chain embedded in DigiCert's reply.

## Verify an OpenTimestamps proof

```
pip install opentimestamps-client
ots info SHA256SUMS.ots
ots upgrade SHA256SUMS.ots
ots verify SHA256SUMS.ots
```

`ots verify` needs a Bitcoin node, or it can use public block explorers. Until upgraded, `ots info` shows only pending calendar attestations.

## Chain of trust

`SHA256SUMS` and `MANIFEST.csv` list the SHA-256 of every document, so proving the date of those two files proves the date of every document they list: check a document with `shasum -a 256 <file>` against the list. `LOG.tsv` is an append-only record (date, file, sha256, TSA, genTime, status). Tool: `systems/timestamp_proofs.py` in the Hillhouse working folder.
