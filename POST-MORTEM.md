# Post-Mortem

## Project

**Codenames: Pictures Duet 5x4 Keycard** is an unofficial fan-made web app for playing Codenames: Pictures with Codenames: Duet rules on a 5x4 grid.

The goal was to keep the app portable, fast, and easy to share: one `index.html`, no build step, no backend, and no required install.

## What Went Well

- The core matrix rule became stable: 2 shared agents, 4 Alpha-only, 4 Bravo-only, 2 cross-risk cards, 1 mutual assassin, and 7 pure bystanders.
- Session IDs became reversible and useful: players can copy a session and reload the exact same keycard later.
- Pass-and-play safety improved a lot. The app now starts locked and returns to LOCK when loading or creating a new card.
- The UI became more game-like and less like a technical dashboard.
- The final layout prioritizes the keycard, especially on mobile and iPad.
- The app remained fully static and deployable on GitHub Pages.

## Main Mistakes

### 1. The Keycard Was Not Prioritized Enough

Early versions gave too much vertical space to headers, labels, controls, and audit tools. This hurt the real use case: quickly reading the keycard during play.

**Learning:** in a game utility, the board/keycard is the product. Everything else must be secondary.

### 2. Audit Mode Broke the Layout

The first audit implementation used a global `debug-mode` class that changed the whole page layout. It looked acceptable in one preview but broke badly in desktop Chrome.

**Learning:** destructive debug layouts are risky in responsive UIs. Audit belongs in a contained modal, not in the main play surface.

### 3. Native Dialogs Were the Wrong Interaction

Using native `confirm()` for audit warnings felt out of place and was unreliable in some embedded browser views.

**Learning:** important game-state warnings should use internal UI so the flow remains consistent across browsers.

### 4. Mobile Ordering Needed More Care

Flex `order` fixes solved one problem but accidentally moved footer/timer/header into strange positions on mobile.

**Learning:** responsive ordering should be reviewed with screenshots, not just assumed from CSS.

### 5. Theme Colors Needed Contrast Metrics

Several theme attempts looked good in isolation but failed as interactive UI: Alpha/Bravo buttons were not always readable, and active/inactive states were unclear.

**Learning:** theme design needs contrast checks and state checks: inactive, hover, active, disabled, and cell colors all matter.

### 6. The Footer Became Too Busy

The footer initially repeated links already present in Refs and later became too large on mobile.

**Learning:** footer should close the page calmly. Primary feedback belongs near the top; secondary links belong in modal/refs.

### 7. Token Semantics Needed to Match Play

Tokens 8-11 were visually distinct but their click cycle briefly changed in a way that made them less useful.

**Learning:** state machines in small UI controls need to preserve player expectations. Time tokens should cycle consistently.

## UX Decisions That Survived

- Start on LOCK every time.
- Show `NEW`, `SESSION ID`, and `LOAD` together.
- Tap Session ID to copy, with feedback.
- Timer starts automatically.
- Timer reset restarts immediately and hides the reset button.
- Tokens 1-7 start available; 8-11 start closed.
- Audit requires an internal confirmation before revealing both keycards.
- Feedback links moved to the header.
- Footer kept short: credits, About, Rules, Refs, and Follow.

## Final Test Checklist

- JavaScript syntax check passes.
- Desktop Chrome headless render passes.
- Mobile Chrome headless render passes.
- App starts on LOCK.
- New card creation does not reveal a keycard before locking.
- Session ID copy gives feedback.
- Session load restores the exact keycard and starts locked.
- Timer reset restarts automatically.
- Tokens 8-11 start closed.
- About, Rules, and Refs are short and usable during play.
- Header feedback links point to BGG and Reddit.
- Footer follow link points to Instagram.

## Deployment Notes

The app is static and ready for GitHub Pages.

Expected GitHub Pages URL:

```text
https://hrxm.github.io/5x4-keycard-app-for-codenames-pictures-duel-house-rule/
```

## Credits

House rule made by Hiro Miyakawa, with thanks to all playtesters.

This is a non-commercial fan-made helper. It is not affiliated with Czech Games Edition, Vlaada Chvatil, or the official Codenames line.
