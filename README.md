# Daily Construction Report

A single-file web app for daily construction reports (based on the City of Whitehorse template): report log grouped by project, editable reports, photo attachments, signature, save as PDF and send by email.

Reports are stored in the browser only. Open `index.html` in a browser, or enable GitHub Pages to host it.

## Security notes

- Reports are stored only in the browser of the person using the app, encrypted (AES-256-GCM, key derived from a passcode with PBKDF2). The app file itself contains no report data.
- The app locks after 5 minutes of inactivity, when the page is hidden for 2 minutes, or when "Lock" is pressed.
- A forgotten passcode cannot be recovered.
- This is a front-end only app. It has no server, so it cannot send a PDF by email on its own and cannot stop someone copying the (empty) app file. See the project notes for what a secure backend would need.
- Keep this repository **private**, and never commit exported reports, PDFs, Word files or credentials (`.gitignore` blocks common ones).
