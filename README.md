# Tender Document Package Builder

A frontend-only web app that turns a set of bidder PDFs into one complete,
checked, correctly ordered tender package PDF. All processing happens in the
browser — no files are ever uploaded to any server.

## Live Demo
https://your-project.vercel.app

## How to Run Locally
1. Clone this repo
2. Open `index.html` with VS Code Live Server (or any static server)
3. Upload `requirements.json`, then the bidder PDFs

## How to Use
1. Load `requirements.json` — tender details and required documents appear.
2. Upload PDF files (max 30 files / 50 MB). Non-PDFs are rejected;
   damaged/password-protected files show an error.
3. Match each file to a requirement (one-to-one). Duplicate files (same
   content) are detected and blocked from matching.
4. Enter expiry dates for documents that have them.
5. Statuses update live: Missing / Expiry date needed / Expired /
   Not provided / OK.
6. When nothing blocks, click **Generate Package** — a combined PDF is
   created with a cover page and `TenderID | Page X of Y` footer on every
   page, downloaded as `&lt;tender_id&gt;_Package.pdf`.
7. Switch between English and Bangla at any time.

## Tech
- Single-file vanilla JS app (`index.html`)
- pdf-lib (merge + footers), pdf.js (page count + validation) via CDN

## Sample Output
See `output/T-2026-0417_Package.pdf` and `screenshots/`.
