# NEON RUSH production roadmap

## Phase 0 — Scope and release rules
- Keep the core runner playable without ads.
- Use only original or properly licensed models, music, sound, fonts, and textures.
- No cash, diamonds, or off-platform prizes are offered by this starter.
- Keep AdsGram Rewarded ads voluntary and tied to a clearly described in-game benefit.
- Do not simulate impressions, force clicks, or show an ad on every action.

## Phase 1 — Stabilize the game loop
- Test collisions for every obstacle type and lane.
- Tune difficulty progression, obstacle spacing, coin placement, pause/resume, and restart.
- Add a tutorial, settings, sound toggle, haptics where supported, and readable game-over feedback.
- Add automated smoke tests for score progression, pause, restart, and game-over state where feasible.

## Phase 2 — Art and audio
- Replace the primitive runner with an original optimized GLB character and animation rig.
- Build modular city/road sections and reusable obstacle prefabs.
- Add licensed/original music and effects with a mute control.
- Use compressed textures and optimized geometry; avoid heavy post-processing on low-end devices.
- Keep the visual language distinct; do not copy another game's characters, UI, or assets.
- Before AdsGram submission, add meaningful original gameplay/content and replace placeholder visuals. AdsGram moderation says template-like or copied apps can be rejected, especially if they offer little beyond displaying ads.

## Phase 3 — Performance and accessibility
- Profile Android devices in Telegram WebView, not only desktop browsers.
- Target stable 30 FPS on supported lower-end devices and 60 FPS on capable devices; measure rather than assume.
- Respect device safe areas, reduce motion/effects on weak devices, handle resize/orientation, and test long sessions for memory growth.
- Consider object pooling for obstacles/coins and pause animation when the app is hidden.

## Phase 4 — Telegram and backend
- Host over HTTPS and configure the Mini App URL in BotFather.
- If adding user accounts or cloud saves, send raw `Telegram.WebApp.initData` to the backend and validate its signature there. Do not trust `initDataUnsafe` for authorization.
- Never ship bot tokens or server secrets to the browser.
- For online leaderboards, validate scores server-side and add rate limiting, replay-resistant run IDs, and basic abuse monitoring.
- Publish privacy, support, and terms information appropriate to the final product and data collected.

## Phase 5 — AdsGram
- Obtain a real Rewarded block ID from the publisher dashboard and complete required moderation.
- Test the SDK and fallback paths with the official procedure.
- Keep the Rewarded action optional and explain the benefit before the ad.
- Grant the prototype's local double-score bonus only when `done === true` and no error is reported.
- For server-backed or valuable rewards, use a backend and the provider's supported verification/reward callback flow; never trust a browser-only callback as proof of valuable rewards.
- Track ad load failures and completion rates without collecting unnecessary personal data.

## Phase 6 — Release gates
- No critical gameplay or console errors in supported browsers.
- Verified Android phone testing at low/medium/high performance classes.
- No unlicensed assets or misleading monetization claims.
- Ads and Mini App behavior verified in Telegram, with approval status confirmed directly in provider dashboards.
- Backups, versioned releases, rollback plan, and a process for fixing crashes.
