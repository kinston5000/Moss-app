# Moss in a Jar

A self-contained relaxation web app with six activities, a customizable moss jar, generated soundscapes and browser-local progress.

## Preview

Run `python3 -m http.server 8000` from this folder, then open http://localhost:8000. No build tools, account or API key are required. Opening index.html directly also runs the core app, but installation and offline caching require HTTPS or localhost.

## Publish after approval

Upload index.html, manifest.webmanifest, sw.js, icon.svg, icon-192.png and icon-512.png together to an HTTPS static host. For GitHub Pages, put those files at the publishing root, configure Pages, then test its actual URL. Relative asset paths also support repository subfolders. Do not publish original.html or private working notes unnecessarily.

Once hosted, send the HTTPS link. On iPhone use Safari → Share → Add to Home Screen. On supported Android browsers use Install app / Add to Home screen. Offline use becomes available after one successful online load. Browser support and installation menus vary.

## What changed

- Added standard HTML document structure, UTF-8 encoding and a mobile viewport.
- Added dynamic viewport sizing and phone safe-area padding.
- Added install metadata, application icons and offline service worker.
- Removed external font requests; the app uses local system fallbacks.
- Removed dependence on Claude's embedded AI bridge. Talk explicitly uses prewritten replies. Live AI would require a separately configured backend and privacy decisions.
- Fixed pending scripted replies so Stop and Clear chat cancel their delayed response.
- Preserved the original Drive file unchanged.

## Privacy and limits

Chats, names and progress are stored in this browser's local storage, not synchronized across devices. Clearing browser site data removes them. This distribution makes no external API or font requests. It has no analytics, user account or server database. The host will still receive ordinary page requests and may retain standard access logs.

Moss is a relaxation companion, not professional care or emergency support. Existing crisis text is Australia-specific and should be reviewed before international distribution. Do not market the app as therapy, a medical treatment or live AI.

## Verification

Passed: JavaScript syntax checks for both inline scripts and service worker, unique HTML IDs, required install/offline asset presence, no Claude bridge calls, no external font dependency, viewport metadata.

Not yet verified: actual browser interactions, audio playback, phone layout, installation or offline reload. Automated Chromium could not launch because this execution workspace disallows its socket operation; the separate browser could not reach the local preview. A browser smoke-test script is included for a suitable environment. A successful syntax check is not a complete functional test.
