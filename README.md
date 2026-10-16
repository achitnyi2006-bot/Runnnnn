# NEON RUSH — Telegram Mini App Production Starter

This is an improved **production-oriented starter**, not a finished commercial release. It keeps the original single-page Three.js runner and adds a configurable AdsGram Rewarded integration, a release checklist, and a staged production plan.

## Included now
- Three-lane 3D endless runner, lane changes, jump, slide, obstacles, collectible coins
- Keyboard, touch buttons, and swipe controls
- Score, coins, local best score, pause, restart, and game-over screen
- Telegram Mini App SDK bootstrap (`ready`, `expand`, theme colors)
- Optional AdsGram Rewarded ad button. It remains hidden until a real Rewarded `blockId` is configured.
- Reward callback checks `result.done === true` and `result.error !== true` before granting the local double-score bonus
- `config.js` for public client configuration (no secrets)
- `PRODUCTION_ROADMAP.md`, `TESTING_CHECKLIST.md`, and `assets/ASSETS_PLAN.md`

## Run locally
Open `index.html` in a modern browser with internet access. The game uses CDN-hosted Telegram and Three.js scripts. Some browsers restrict local-file behavior; if so, use a local static server or GitHub Pages.

## GitHub Pages deployment
1. Extract the ZIP.
2. Upload the **contents** of `neon_rush_prototype/` to the root of a GitHub repository. `index.html` and `config.js` must be in the repository root.
3. Open **Settings → Pages** and publish from the `main` branch, `/(root)`.
4. Open the generated HTTPS URL and test it on an Android phone.
5. Configure the HTTPS Mini App URL with your Telegram bot using BotFather.

## AdsGram setup (optional; do not guess a block ID)
1. Create/register your platform in the AdsGram publisher dashboard and complete its required setup/moderation.
2. Create a **Reward** ad unit and copy the actual Rewarded `blockId` from the dashboard.
3. Edit `config.js` and set `adsgramRewardedBlockId` to that real ID. Do not use an Interstitial ID for this Rewarded slot.
4. Deploy the changed files, then test only with the supported AdsGram test/debug procedure before relying on real traffic.
5. The optional button appears on the game-over screen. The player chooses whether to watch. A bonus is granted only if the SDK result confirms completion. If no ad is available or the ad fails, no bonus is granted.

Official AdsGram documentation:
- Rewarded / Interstitial integration: https://docs.adsgram.ai/publisher/reward-interstitial-integration
- Get a block ID: https://docs.adsgram.ai/publisher/get-block-id
- Code examples: https://docs.adsgram.ai/publisher/reward-interstitial-code-examples

**Important:** AdsGram moderation may reject template-like/copycat apps or apps with little functionality beyond ads. Customize the game with meaningful original content before submitting. This client-only bonus is a prototype convenience, not secure evidence for a competitive online leaderboard or anything of real-world value. If scores or rewards become valuable/competitive, move validation to a backend and verify Telegram `initData` server-side. Never put Telegram bot tokens or API secrets in `config.js` or any frontend file.

## What is not production-ready yet
- The player and city are procedural placeholder geometry, not premium licensed/original 3D assets.
- No server-side profile, leaderboard, cloud saves, analytics, or anti-cheat.
- No sound/music, accessibility options, onboarding flow, content moderation workflow, or privacy/support pages.
- No real-device performance, battery, crash, or AdsGram approval results are claimed.
- The current game and ad integration must be tested after deployment; loading the page is not proof of a successful ad impression or monetization.

See `PRODUCTION_ROADMAP.md` and `TESTING_CHECKLIST.md` before release.
