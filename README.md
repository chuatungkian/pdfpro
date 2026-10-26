# pdfpro

A private, offline PDF workspace packaged as one HTML file. The current `index.html` is **20.21 MB** and includes its PDF engines, English OCR model, Inter font and downloadable source bundle.

## Use

Download `index.html` (or the identical `pdfpro.html`) and open it in a current desktop browser. The app needs no installation, account or network connection after download. PDFs are processed on your device.

The workspace includes document tabs, local recovery, annotations and freehand drawing, page organisation, added text/images, forms, OCR, comparison, encryption, redaction, signatures and exports. The page toolbar can float, minimise, or lock across the top or bottom of the working area.

IndexedDB retains documents and edits when permitted by the browser. Its availability for local files depends on the browser; check the save indicator. Local recovery may include unlocked copies, originals and undo history. Download important work and use Library to remove closed stored copies when needed.

## Documentation and verification

- [User guide and limitations](README.txt)
- [Validation results](VALIDATION.txt): 781 automated assertions, including controlled DOM tests with real PDF processing. Live browser visual verification remains unavailable for this revision.
- [Checksums](SHA256SUMS.txt)

pdfpro is an offline PDF toolkit. It does not claim complete Adobe Acrobat feature parity, PDF/A or PDF/UA certification, or certificate identity/trust validation.

## Source and rebuild

The complete application source kit is available in [pdfpro-3.0-app-source.zip](pdfpro-3.0-app-source.zip). The same file contents can be exported offline using **About & source > Download source bundle**.

Extract the source kit, enter its `source` folder and install the locked dependencies with `pnpm install --frozen-lockfile`. From the repository root, run `python upstream/assemble-mupdf-source.py` to reconstruct the [complete MuPDF source archive](upstream/README.md) from its three verified parts. Copy the resulting `upstream/mupdf-1.28.1-source.tar.gz` beside `build.mjs`, then run `node build.mjs`. See README.txt for the exact runtime versions, test dependencies and build details. No user PDFs, browser storage, credentials or signing keys are included in this repository.

## Licence

pdfpro is distributed under [AGPL-3.0-or-later](LICENSE.txt). Components retain their own licences; see [third-party notices](THIRD-PARTY-NOTICES.txt). The full MuPDF corresponding source is retained under `upstream/` in losslessly reassembled parts.
