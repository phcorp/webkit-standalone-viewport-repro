# Standalone viewport repro

Minimal test case for a WebKit bug report: a Home Screen web app
(`display: standalone`, `viewport-fit=cover`) keeps a viewport shorter than the
screen after navigating to an out-of-scope page and back.

1. Open `app/` on an iPhone, add it to the Home Screen and launch it from there.
2. Tap "Leave the app's scope and come back".
3. Bug: a red band appears under the green line, and `innerHeight` is smaller
   than `screen.height`.
