# PDF Parsing & Extraction Pipeline

This repository contains a single-file PDF parsing pipeline (`parse_pdfs.py`) that:
- downloads PDFs from URLs (CSV-driven),
- extracts text & tables (pdfplumber, pdfminer, Camelot, OCR fallback),
- classifies into `bulk_deal` / `board_meeting` / `hybrid` / `generic`,
- extracts structured fields (records / details),
- outputs ordered JSON to `parsed_results.json`.

## Files
- `parse_pdfs.py` - main script (single-file pipeline)
- `requirements.txt` - Python dependencies
- `Dockerfile` - container image definition
- `sample_output/parsed_results.json` - example output

## Running locally (native Python)
1. Create a CSV `Documents.csv` with a column `document_urls`. Example:
```csv
document_urls
https://example.com/file1.pdf
https://example.com/file2.pdf

pip install -r requirements.txt

python parse_pdfs.py --input Documents.csv --output parsed_results.json

docker run --rm -v $(pwd):/app pdf-parser python parse_pdfs.py --input Documents.csv --output parsed_results.json


