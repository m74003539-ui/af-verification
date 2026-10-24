# AF Verification 🔐

Starter website with a black-and-gold theme. Visitors select Google or WhatsApp Web, enter their own email address, receive a Firebase email-link sign-in email, and are redirected to the official destination after the link is completed.

## Important behavior
- This is an independent redirect page, not a Google or WhatsApp login page.
- Firebase email-link sign-in proves access to the email address; it does not sign the visitor into Google or WhatsApp.
- Never ask for or store Google/WhatsApp passwords or one-time codes.
- The website is not live and will not send emails until Firebase is configured and the site is hosted on HTTPS.

## Firebase setup
1. Open https://console.firebase.google.com/ and create a Firebase project.
2. In **Authentication → Sign-in method**, enable **Email link (passwordless sign-in)**.
3. In **Authentication → Settings → Authorized domains**, add the eventual hosting domain.
4. In **Project settings → General → Your apps**, register a Web app and copy its Firebase configuration.
5. Edit `index.html` and replace the placeholder values for `apiKey`, `authDomain`, `projectId`, and `appId` with the real config.
6. Host the files on HTTPS and test with an email address you control.

## GitHub Pages
1. Create a GitHub repository named `af-verification`.
2. Upload `index.html` and `README.md` to the repository root.
3. Open **Settings → Pages**, select the `main` branch and `/ (root)`.
4. After GitHub Pages publishes the site, add that domain to Firebase Authorized domains.

## Destinations
The `destinations` object in `index.html` points to `https://accounts.google.com/` and `https://web.whatsapp.com/`.
