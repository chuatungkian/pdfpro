# pdfpro

An offline PDF workspace packaged as one HTML file. The current `index.html` is **20.33 MB** and includes its PDF engines, English OCR model, Inter font and downloadable source bundle.

## Use

Download `index.html` (or the identical `pdfpro.html`) and open it in a current desktop browser. The app needs no installation, account or network connection after download. PDFs are processed on your device.

The workspace includes document tabs, local recovery, continuous page scrolling, annotations and freehand drawing, page organisation, added text/images, forms, OCR, comparison, encryption, redaction, signatures and exports. The page toolbar can float, minimise, or lock across the top or bottom of the working area.

**Organise > Merge & split** combines current edited PDFs from open tabs, the local library or uploads. Reorder sources, add visual split points or grouped page ranges, preview filenames, download grouped PDFs as a ZIP, or create a merged working tab. Plans recover locally and detect changed or missing sources.

**Edit > Add link** supports websites, email addresses and pages in the same PDF. Draw the link area, set the destination, then choose Done to follow links. The small arrow edits or removes a link. Native PDF links survive undo/redo, exports and local recovery. OCR phrase search and plain-text line grouping are also checked in this revision.

IndexedDB retains documents and edits when permitted by the browser. Its availability for local files depends on the browser; check the save indicator. Local recovery may include unlocked copies, originals and undo history. Download important work and use Library to remove closed stored copies when needed.

## Documentation and verification

- [User guide and limitations](README.txt)
- [Validation results](VALIDATION.txt): 1,270 counted assertions passed, plus certificate-signing and package-integrity checks. Tests use real PDF processing and embedded engines in controlled DOM/worker runtimes.
- [Feature audit](FEATURE-AUDIT.txt): all 64 distinct tool actions mapped to regression workflows. Live browser layout, external navigation, downloads and print-dialogue behaviour remain unverified.
- [Checksums](SHA256SUMS.txt)

pdfpro is an offline PDF toolkit. It does not claim complete Adobe Acrobat feature parity, PDF/A or PDF/UA certification, or certificate identity/trust validation.

## Source and rebuild

The complete application source kit is available in [pdfpro-3.0-app-source.zip](pdfpro-3.0-app-source.zip). The same file contents can be exported offline using **About & source > Download source bundle**.

Extract the source kit, enter its `source` folder and install the locked dependencies with `pnpm install --frozen-lockfile`. From the repository root, run `python upstream/assemble-mupdf-source.py` to reconstruct the [complete MuPDF source archive](upstream/README.md) from its three verified parts. Copy the resulting `upstream/mupdf-1.28.1-source.tar.gz` beside `build.mjs`, then run `node build.mjs`. See README.txt for the exact runtime versions, test dependencies and build details. No user PDFs, browser storage, credentials or signing keys are included in this repository.

## Licence

pdfpro is distributed under [AGPL-3.0-or-later](LICENSE.txt). Components retain their own licences; see [third-party notices](THIRD-PARTY-NOTICES.txt). The full MuPDF corresponding source is retained under `upstream/` in losslessly reassembled parts.
