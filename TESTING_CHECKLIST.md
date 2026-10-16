# NEON RUSH test checklist

## Local smoke test
- [ ] `index.html` loads with an internet connection and no fatal console error.
- [ ] Start, pause, resume, game over, run again, and main menu work.
- [ ] Left/right controls stay within three lanes.
- [ ] Jump avoids low hazards; slide avoids overhead hazards; normal obstacles cause game over on collision.
- [ ] Coins can be collected; score and coin count update.
- [ ] Best score persists after reload on the same browser/device.
- [ ] Swipe controls and on-screen buttons both work on touch devices.
- [ ] Resize/orientation changes do not leave the canvas distorted.

## Telegram Mini App test
- [ ] HTTPS URL opens through the Telegram bot.
- [ ] Telegram WebApp `ready()`/`expand()` calls do not cause errors.
- [ ] Test the actual Telegram Android WebView, not only an external browser.
- [ ] Check safe areas, screen notches, browser back behavior, and app minimize/resume.

## AdsGram test (only after a real Rewarded block ID is issued)
- [ ] `config.js` contains the actual Rewarded ID, not a placeholder.
- [ ] Button is hidden when no ID is configured.
- [ ] Ad load failure, no-fill, cancellation, and SDK errors grant no bonus.
- [ ] Only a successful completed Rewarded result grants the bonus.
- [ ] Core gameplay remains available if AdsGram fails or is unavailable.
- [ ] Provider dashboard shows expected test/production behavior; do not infer revenue from a button click.

## Device/performance test
- [ ] Test at least one lower-end Android device and one stronger device.
- [ ] Measure FPS and loading time over a 10–15 minute session.
- [ ] Check heat, battery use, memory growth, and crashes.
- [ ] Confirm no runaway growth in obstacle/coin objects after long play.

## Release decision
Do not call the game production-ready until the critical items are checked on real devices and the relevant provider approval is confirmed.
