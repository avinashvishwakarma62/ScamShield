# ScamShield

A responsive, local-first digital safety education app for spotting common scam patterns. Static HTML/CSS/JavaScript with optional Vercel serverless AI assistance.

## Run locally

Serve this folder over HTTP because browser ES modules are restricted on `file://`. For example, run `python -m http.server 8000` from this folder and open `http://localhost:8000`. No API key, build step, dependency install, or account is required for core features. Optional AI functions require Vercel deployment and environment variables.

## GitHub + Vercel

1. Create a GitHub repository and upload the contents of this folder.
2. Import the repository into Vercel. Choose **Other**; no build command is needed, and the root is the output directory.
3. Deploy. Vercel detects the functions in `api/`.
4. Optional AI: in Vercel Project Settings → Environment Variables, set `OPENAI_API_KEY` and `OPENAI_MODEL` to a model available to your account, then redeploy. The key remains server-side.
5. Never commit a real API key. `.env.example` documents the optional names.

Without variables, the analyzer uses browser-side local rules. `api/url-check.js` does not claim domain reputation; connect a reputable provider server-side if available and review its privacy terms.

## Included features

- Message, email, WhatsApp, URL checks, screenshot preview and manual transcription fallback
- Explainable 0–100 score, low/medium/high bands, matched reasons, categories and recommendations
- UPI/payment, KYC/impersonation, investment and job/task scam patterns
- Emergency checklist and India reporting links, local dashboard/history, knowledge guides and quiz
- English/Hindi/Hinglish selector, responsive layout, keyboard support, skip link, accessible labels and reduced-motion support
- No third-party client scripts; local checks work without a backend

## Privacy and limits

Local checks run in the browser; up to 30 history records are stored in localStorage on the device. When optional AI is enabled, submitted text is sent to your Vercel function and configured model provider. Never submit passwords, OTPs, PINs, card details, or sensitive identity documents. The rule engine can miss scams or flag legitimate text and is not a live malware/domain reputation service. HTTPS and a low score do not prove safety. Verify via official channels you find independently.

Screenshot OCR is not bundled. The image is previewed locally and users can type/paste visible text, avoiding upload of personal screenshots to an unconfigured OCR provider.

## Structure

`index.html`, `css/`, `js/`, `data/`, `assets/logo.svg`, `api/`, `.env.example`, `vercel.json`, `package.json`.
