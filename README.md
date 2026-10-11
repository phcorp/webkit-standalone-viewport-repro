# Standalone viewport repro

Minimal test case for a WebKit bug report: a Home Screen web app
(`display: standalone`, `viewport-fit=cover`) keeps a viewport shorter than the
screen after navigating to an out-of-scope page and back.

1. Open `app/` on an iPhone, add it to the Home Screen and launch it from there.
   The white area fills the screen and the green line sits on the bottom edge.
2. Tap "Leave the app's scope and come back".
3. Bug: a red band appears under the green line; `innerHeight` and `100vh` are
   smaller than `screen.height`. Rotating to landscape and back clears it.
