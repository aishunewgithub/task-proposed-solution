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
1. Create a CSV `Documents.csv` with a column `document_urls`. Each cell should be like:
