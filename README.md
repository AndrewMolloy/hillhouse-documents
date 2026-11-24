# Hillhouse public-records vault

This repository holds copies of documents published by public bodies about the Hillhouse Technology Enterprise Zone, Thornton-Cleveleys: every version we hold of every Wyre Council download on the subject, and Environment Agency reports published on GOV.UK. It is kept as a permanent, timestamped public record by **Hillhouse Watch** ([hillhousewatch.uk](https://hillhousewatch.uk)).

It began in July 2026 as downloadable copies of Wyre Council's contamination reports, which the council then published only through the Issuu viewer.

Until October 2026, the council published three of these reports only through **Issuu**, a page-flipping viewer that could not be downloaded or reliably read with a screen reader. On 14 and 15 October 2026, after an accessibility complaint, the council replaced the Issuu viewers with downloadable PDFs that have a real text layer.

**The files at the top level are now the council's own downloads, unchanged.** The searchable copies we made from Issuu in July 2026 are kept in `archive/issuu-ocr-2026-07-15/`.

**Nothing in these documents has been altered.** Every file is the publisher's bytes, as downloaded. If a source document is later amended, re-redacted or removed, the git history here preserves what was published and when.

## How to use and verify

- Clone: `git clone https://github.com/AndrewMolloy/hillhouse-documents.git`
- Verify every file against its recorded hash: `sha256sum -c SHA256SUMS` (on macOS: `shasum -a 256 -c SHA256SUMS`).
- `MANIFEST.csv` lists every file with its publisher, title, source URL, the date and time it was fetched (UTC), SHA-256, size, page count, status (current, superseded, or removed by the publisher on a date) and a note.
- Top-level files are the council's current files. `wyre/<file number>-<name>/` holds the other Wyre downloads, one folder per council file number, with the fetch date at the start of each filename. `ea/` holds Environment Agency reports. Where two council file numbers served identical bytes, one copy is kept and the note in `MANIFEST.csv` gives the other number. Files already at the top level are not repeated under `wyre/`; `MANIFEST.csv` gives their council file number.

## Current documents (the council's own files)

| File | What it is | Council source (fetched 21 Oct 2026) | Council file date | SHA-256 |
|---|---|---|---|---|
| `phase1-thornton-soil-investigation-dec2024.pdf` | WSP Phase 1 (preliminary) offsite soils investigation, factual report, December 2024. 461 pp. | [wyre.gov.uk/downloads/file/2607](https://www.wyre.gov.uk/downloads/file/2607/factual-report-from-preliminary-phase-of-offsite-soils-investigation) | 15 Oct 2026 | `f551ecfd…d959` |
| `occupation-road-interpretative-report-feb2026.pdf` | WSP Occupation Road Allotments interpretative site investigation report, February 2026. 183 pp. | [wyre.gov.uk/downloads/file/2608](https://www.wyre.gov.uk/downloads/file/2608/occupation-road-allotments-interpretative-site-investigation-report) | 15 Oct 2026 | `9cda43f8…5426` |
| `occupation-road-produce-summary-mar2025.pdf` | Occupation Road Allotments: produce sampling results and summary, March 2025. 2 pp. | [wyre.gov.uk/downloads/file/2610](https://www.wyre.gov.uk/downloads/file/2610/produce-sampling-results-and-summary-march-2025-occupation-road-allotments-) | 15 Oct 2026 | `885c97fa…c0db8` |
| `occupation-road-produce-data-mar2025.ods` | Occupation Road produce data (spreadsheet). | [wyre.gov.uk/downloads/file/2611](https://www.wyre.gov.uk/downloads/file/2611/occupation-road-produce-data) | 15 Oct 2026 | `e6f3145d…a66f` |
| `phase3-factual-report-mar2026.pdf` | WSP Phase 3 grid investigation factual report, March 2026. 1,762 pp. | [wyre.gov.uk/downloads/file/2452](https://www.wyre.gov.uk/downloads/file/2452/phase-3-factual-report) | 14 May 2026 | `65774aa1…fcd61` |

Full SHA-256 hashes are in `SHA256SUMS`. The Phase 2 factual report (council file 2604) is no longer a current council file; see the section below.

## The Phase 2 factual report: two versions

| File | What it is | SHA-256 |
|---|---|---|
| `phase2-residential-grid-factual-report-jul2025.pdf` | The original, council file 2604, as downloaded on 21 Oct 2026. 485 pages. The council removed it from its website on 22 Oct 2026 (the address now returns "not found"). | `5035b0ba…db0729` |
| `phase2-residential-grid-factual-report-jul2025-republished-2026-11-11-redacted.pdf` | The version the council republished on 11 Nov 2026 as file 2625. 353 pages. It is 132 pages shorter: the 132 pages of trial-pit logs (original pp. 86 to 217) are not in it, two staff names are redacted, and the surveyed sample coordinates (which were on the trial-pit logs) are no longer present. | `810418b7…5ce8` |

Both are kept here for comparison. Also from 11 Nov 2026: `phase2-interpretative-report-mar2026.pdf` (council file 2627, 46 pages, new on the council site).

**Accessibility notes on the council's versions.** They are a real improvement, but:
- appendix pages pasted in from other PDFs (lab certificates, logs and tables) carry no structure tags;
- the Phase 1 lab QA/QC page (PDF p.456) has no text layer;
- the Phase 1 summary results table (pp.458 to 460) shows "below detection" by colour only.

## Archive: our July 2026 copies made from Issuu

| File | Notes |
|---|---|
| `archive/issuu-ocr-2026-07-15/phase1-thornton-soil-investigation-dec2024.pdf` | Captured from the council's Issuu viewer, with an OCR text layer added and images downsampled. The OCR misreads many numbers, so use the current file above for figures. |
| `archive/issuu-ocr-2026-07-15/occupation-road-interpretative-report-feb2026.pdf` | As above. |

We compared these page by page with the council's October 2026 downloads:
- They are the same documents, with the same page count and the same redactions.
- No page shows content in one version that is missing from the other.

## Environment Agency EIR release: AGC PFOA and PFAS compliance work (EIR2026/53951)

`ea/eir2026-53951-agc-pfoa-2026-11/` holds the 77 files the Environment Agency released in response to an Environmental Information Regulations 2004 request about the installation operated by AGC Chemicals Europe Ltd at Hillhouse (permit EPR/BU5453IY). The request is public on WhatDoTheyKnow: [current_pfoa_releases_from_agc_c](https://www.whatdotheyknow.com/request/current_pfoa_releases_from_agc_c). The Environment Agency's response letter is dated 17 November 2026 (reference EIR2026/53951); the files were downloaded from the Agency's secure link on 23 November 2026. The files include reports and letters written by AGC Chemicals Europe Ltd and by its consultants, and the Agency's own response letter and Regulation 61 notice.

- Every file is republished exactly as the Environment Agency released it, with the Agency's file names. Nothing here has been altered; redactions are the Agency's.
- Some files carry markings such as "Confidential" or "AGC Group Internal Use Only". The Environment Agency released them under the Regulations. `MANIFEST.csv` notes which files contain such wording.
- The folder also holds the original zip (`EA-EIR2026-53951-all-files-2026-11-23.zip`) as downloaded.
- The Agency's own secure download link expires on 7 December 2026 at 23:59. These copies are republished so that the release stays available.
- Each file's SHA-256 fingerprint is in `SHA256SUMS` and `MANIFEST.csv`.

Scope: documents in this repository are republished exactly as the public body released them.

## Proof of date

`SHA256SUMS` and `MANIFEST.csv` list the SHA-256 fingerprint of every file here. On 12 Nov 2026 we sent only those two files' fingerprints (never the documents) to two independent timestamp authorities (FreeTSA and DigiCert, RFC 3161) and to the OpenTimestamps service, which anchors them to the Bitcoin blockchain. The signed replies are in `timestamps/2026-11-12/`, with the certificates needed to check them and instructions in `timestamps/README.md`. Anyone can verify with `openssl ts -verify` and `ots verify`. This shows these files existed in this form no later than that time; it does not show a document is accurate or complete beyond what its publisher released. The Bitcoin proofs start as pending and are upgraded after a few hours.

On 24 Nov 2026 the same was done for the updated `SHA256SUMS` and `MANIFEST.csv` (including the Environment Agency EIR2026/53951 release); the proofs are in `timestamps/2026-11-24/`. The OpenTimestamps proofs there were pending Bitcoin confirmation when added and are upgraded later.

## What is not here, and why

Only documents that a public body has published are here. Not included: confidential or third-party material, correspondence received privately, replies to information requests that are not already public, and our own drafts and analysis. We have added no personal or family details of our own: every document is exactly as its publisher released it. Council pages (as opposed to downloadable files) are not copied.

## Sources and attribution

The contamination reports were authored by WSP for the Environment Agency and published by Wyre Council as environmental information. The Environment Agency reports were published by the Environment Agency on GOV.UK. Each file's source URL is in `MANIFEST.csv`. These copies are provided for accessibility and public-record purposes only.

## Changelog

- **2026-11-24:** Added the Environment Agency's EIR2026/53951 release (77 files and the original zip, under `ea/eir2026-53951-agc-pfoa-2026-11/`), with `MANIFEST.csv` and `SHA256SUMS` entries and new timestamp proofs. Moved the Phase 2 factual report (council file 2604, removed by the council on 22 Oct 2026) out of the current-documents table; the file itself is unchanged.
- **2026-11-12:** Added trusted timestamp proofs (`timestamps/`). No document was changed.
- **2026-11-12:** Expanded to every version of every Wyre Council download we hold on the subject (under `wyre/`), added the council's republished Phase 2 factual report and the Phase 2 interpretative report, added Environment Agency PFAS reports published on 12 Nov 2026 (under `ea/`), and added `MANIFEST.csv`. No existing file was changed or moved.
- **2026-10-21:** The council's own downloadable PDFs (published 14 and 15 Oct 2026) became the current files. The Issuu-derived copies moved to `archive/issuu-ocr-2026-07-15/`. Added the Phase 2 factual report and the Occupation Road produce summary and data. Added `SHA256SUMS`.
- **2026-07-15:** Initial mirror of the Phase 1 report, the Occupation Road interpretative report and the Phase 3 factual report.
