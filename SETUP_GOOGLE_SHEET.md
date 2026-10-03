# Fasal Mandi — Free Google Sheet Order Storage

## What this does
Every farmer who submits the **Sell / pickup request** can be written to your Google Sheet.

The sheet stores:
- Order ID
- Date/time
- Farmer name
- Phone
- Village/area
- Product
- Variety
- Quantity + unit
- Stock status
- Expected price
- Pickup date
- Landmark
- Notes
- Status (starts as Pending)

## One-time setup

### 1. Create the sheet
Sign in to Google with **asikur591@gmail.com** and create a blank Google Sheet.
You can name it `Fasal Mandi Orders`.

### 2. Add the Apps Script
Open the sheet:
**Extensions → Apps Script**

Delete the default code and paste the contents of `google-apps-script.gs`.

Save the project.

### 3. Deploy it
In Apps Script:
**Deploy → New deployment**

Select:
- Type: **Web app**
- Execute as: **Me**
- Who has access: **Anyone**

Click **Deploy** and approve Google's permission prompts.

Copy the Web app URL. It normally ends with `/exec`.

### 4. Connect the website
Open `fasal-mandi-google-sheet.html` in a text editor.

Find:
`const GOOGLE_SHEET_WEB_APP_URL = 'PASTE_YOUR_GOOGLE_APPS_SCRIPT_URL_HERE';`

Replace the placeholder with your Web app URL.

Example:
`const GOOGLE_SHEET_WEB_APP_URL = 'https://script.google.com/macros/s/XXXXXXXX/exec';`

Save the HTML and upload it to GitHub Pages.

### 5. Test
Open the public Fasal Mandi website → **Sell** → complete a test request.

Then open the Google Sheet. A new **Sell Requests** tab should contain the submission.

## Important
- The website is public, so anyone can submit a request.
- Keep the Google Sheet private; do not publish its sharing link.
- The site currently uses `no-cors` for the browser-to-Google submission. The farmer sees the normal success screen; the Google Sheet receives the data.
- For a production system, add spam protection, validation, authentication/admin controls, privacy notice and a proper database.
