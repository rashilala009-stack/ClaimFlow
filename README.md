# ClaimFlow MVP

A beginner-friendly Flask application for uploading insurance claim PDFs, extracting selectable PDF text, storing claim records locally, and recording a manual review status.

## Features
- Claimant name + PDF upload (PDF only, 10 MB maximum)
- PDF text extraction using `pypdf`
- Dashboard with total, pending, approved and needs-correction counts
- Claim detail page showing extracted text
- Manual review status and reviewer note
- SQLite database created automatically on first run

## Run on Windows / VS Code

1. Open this `ClaimFlow_MVP` folder in VS Code.
2. Open Terminal (**Terminal → New Terminal**).
3. Create a virtual environment:

   ```powershell
   py -m venv venv
   ```
4. Activate it:

   ```powershell
   .\venv\Scripts\Activate.ps1
   ```

   If PowerShell blocks activation, run `venv\Scripts\activate.bat` in Command Prompt instead.
5. Install packages:

   ```powershell
   pip install -r requirements.txt
   ```
6. Start the application:

   ```powershell
   python app.py
   ```
7. Open the local address printed in the terminal, usually `http://127.0.0.1:5000`.

The database file `claimflow.db` and uploaded PDFs are created automatically inside this folder.

## Test it
- Upload a normal text-based PDF with a claimant name.
- Confirm that the extracted text appears on the claim page.
- Change the status to Approved or Needs Correction and save.
- Return to the dashboard and confirm the status and counts update.
- Try a non-PDF file and confirm it is rejected.
- Try a scanned/image-only PDF: it may upload but show that no selectable text was found.

## MVP limitations / future improvements
- No OCR for scanned PDFs yet.
- No login, user roles, or production-grade access controls.
- No AI decision-making, fraud detection, or automatic claim approval.
- SQLite is intended for a local demo; deployment needs stronger configuration and storage controls.

**Privacy:** Use dummy/sample documents only. Do not upload real personal, medical, bank, or insurance information to this demo.
