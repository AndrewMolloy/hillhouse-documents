# Hillhouse contamination reports: accessible copies

These are downloadable copies of Wyre Council's official contamination reports for the **Hillhouse Technology Enterprise Zone, Thornton-Cleveleys**, kept as a permanent, timestamped public record by **Hillhouse Watch** ([hillhousewatch.uk](https://hillhousewatch.uk)).

Until October 2026, the council published three of these reports only through **Issuu**, a page-flipping viewer that could not be downloaded or reliably read with a screen reader. On 14 and 15 October 2026, after an accessibility complaint, the council replaced the Issuu viewers with downloadable PDFs that have a real text layer.

**The files at the top level are now the council's own downloads, unchanged.** The searchable copies we made from Issuu in July 2026 are kept in `archive/issuu-ocr-2026-07-15/`.

**Nothing in these documents has been altered.** If a source document is later amended, re-redacted or removed, the git history here preserves what was published and when.

## Current documents (the council's own files)

| File | What it is | Council source (fetched 21 Oct 2026) | Council file date | SHA-256 |
|---|---|---|---|---|
| `phase1-thornton-soil-investigation-dec2024.pdf` | WSP Phase 1 (preliminary) offsite soils investigation, factual report, December 2024. 461 pp. | [wyre.gov.uk/downloads/file/2607](https://www.wyre.gov.uk/downloads/file/2607/factual-report-from-preliminary-phase-of-offsite-soils-investigation) | 15 Oct 2026 | `f551ecfd…d959` |
| `phase2-residential-grid-factual-report-jul2025.pdf` | WSP Phase 2 residential grid investigation, factual report, July 2025. 485 pp. | [wyre.gov.uk/downloads/file/2604](https://www.wyre.gov.uk/downloads/file/2604/phase-2-factual-report) | 14 Oct 2026 | `5035b0ba…db0729` |
| `occupation-road-interpretative-report-feb2026.pdf` | WSP Occupation Road Allotments interpretative site investigation report, February 2026. 183 pp. | [wyre.gov.uk/downloads/file/2608](https://www.wyre.gov.uk/downloads/file/2608/occupation-road-allotments-interpretative-site-investigation-report) | 15 Oct 2026 | `9cda43f8…5426` |
| `occupation-road-produce-summary-mar2025.pdf` | Occupation Road Allotments: produce sampling results and summary, March 2025. 2 pp. | [wyre.gov.uk/downloads/file/2610](https://www.wyre.gov.uk/downloads/file/2610/produce-sampling-results-and-summary-march-2025-occupation-road-allotments-) | 15 Oct 2026 | `885c97fa…c0db8` |
| `occupation-road-produce-data-mar2025.ods` | Occupation Road produce data (spreadsheet). | [wyre.gov.uk/downloads/file/2611](https://www.wyre.gov.uk/downloads/file/2611/occupation-road-produce-data) | 15 Oct 2026 | `e6f3145d…a66f` |
| `phase3-factual-report-mar2026.pdf` | WSP Phase 3 grid investigation factual report, March 2026. 1,762 pp. | [wyre.gov.uk/downloads/file/2452](https://www.wyre.gov.uk/downloads/file/2452/phase-3-factual-report) | 14 May 2026 | `65774aa1…fcd61` |

Full SHA-256 hashes are in `SHA256SUMS`.

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

## Sources and attribution

All reports were authored by WSP for the Environment Agency and published by Wyre Council as environmental information. These copies are provided for accessibility and public-record purposes only.

## Changelog

- **2026-10-21:** The council's own downloadable PDFs (published 14 and 15 Oct 2026) became the current files. The Issuu-derived copies moved to `archive/issuu-ocr-2026-07-15/`. Added the Phase 2 factual report and the Occupation Road produce summary and data. Added `SHA256SUMS`.
- **2026-07-15:** Initial mirror of the Phase 1 report, the Occupation Road interpretative report and the Phase 3 factual report.
