# Security Policy

## Supported Versions

Only the latest release on `main` is supported with security fixes.

| Version | Supported |
| --- | --- |
| 1.2.x  | ✅ |
| < 1.2  | ❌ |

## Reporting a Vulnerability

Please do **not** report security problems in public issues, discussions, or pull requests.

1. Open the repository's **Security** tab and choose **Report a vulnerability**
   (GitHub private vulnerability reporting).
2. Include as much of the following as you can:
   - affected version (shown as `vX.Y.Z` in the app's 更新与版本 dialog),
   - browser and operating system,
   - steps to reproduce (a minimal construction or input helps a lot),
   - impact, and any proof-of-concept you are comfortable sharing.

You can expect an initial reply within 7 days. For confirmed issues we aim to ship a fix or
mitigation within 30 days, and we will keep you informed while it is being worked on.
Please give us a reasonable window to release a fix before any public disclosure.

## Scope

In scope:

- `math.html` — the single-file app (300k+ lines of HTML/CSS/JS):
  - script injection through AI responses, imported files (`.ggb`, snapshots, share links),
  - unsafe handling of user-supplied text/expressions,
  - data loss or corruption in autosave / share / import-export paths.
- The optional AI and online-share integrations, including API-key handling.

Out of scope:

- Issues that require an already compromised browser, operating system, or extension.
- Denial of service through extremely large constructions or pathological expressions.
- Vulnerabilities in third-party services (GitHub, model providers) — please report those upstream.

## Local data

- The canvas snapshot and app settings are stored in the browser's `localStorage`.
- The AI API key is kept in the browser only, and is sent only to the model endpoint you configure.
- Imported files and share links are processed locally; nothing is uploaded unless you explicitly use AI or online sharing.
