# FORM. 1.1.0 deployment

Upload index.html, sw.js, manifest.webmanifest, icon.svg, icon-192.png, icon-512.png to the root of TimHS98/form-fitness. GitHub Pages source: main, / (root).

Google Cloud: External audience, add both test users, Drive API enabled, drive.file scope, authorized JS origin https://timhs98.github.io. No client secret.

Open the hosted site, use Connect Google Drive and consent. Each account gets separate browser data and its own FORM Fitness folder. The browser-only OAuth token expires and requires a reconnect gesture. No background sync when the app is closed.

Test before using for real: create a sample workout, sync, sign in on another device, verify the history; switch accounts and verify isolation; disconnect internet, log and reconnect; verify data survives an app reload.

The app creates append-only full-state JSON snapshots, including previous revisions. It detects divergent heads and pauses sync for a manual version choice (not automatic record merging). Snapshots consume Drive storage and are not pruned in this release. Old local HTML files have a different browser origin; their data is not transferred automatically. Optional emergency import is available. Data format is v1, compatible with the original FORM backup; unknown schema versions are rejected. Future releases must implement and test actual migrations, retain old data, bump service-worker cache version and app release.

Never commit fitness records, OAuth secrets or access tokens. Only the public browser Client ID belongs in app source.
