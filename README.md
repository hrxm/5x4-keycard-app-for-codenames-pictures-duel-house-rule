# Codenames: Pictures Duet 5x4 Keycard

Unofficial fan-made pass-and-play keycard helper for playing **Codenames: Pictures** with **Codenames: Duet** rules on a 5x4 grid.

This project is a single-file web app: open `index.html` in a browser and play.

## What It Does

- Generates paired Alpha/Bravo 5x4 Duet-style keycards.
- Keeps the 20-card identity of Codenames: Pictures.
- Starts locked for pass-and-play safety.
- Includes a timer, time tokens, session restore, theme switching, and end-game audit.
- Works offline after the page is loaded.

## House Rule Summary

Use 20 Codenames: Pictures cards in a 5 columns x 4 rows grid.

Start with **7 time tokens** for the standard version. Use **8 tokens** for an easier first play.

Each player sees:

- 7 agents
- 2 assassins
- 11 non-agents

The team wins by finding all **12 unique agents**.

Hidden matrix:

- 2 shared agents
- 4 Alpha-only agents
- 4 Bravo-only agents
- 1 Alpha agent / Bravo assassin cross-risk
- 1 Bravo agent / Alpha assassin cross-risk
- 1 mutual assassin
- 7 pure bystanders

Play like Codenames: Duet. When time tokens are gone, sudden death begins: no more clues, and any wrong guess loses.

## How To Use

1. Open `index.html`.
2. Arrange 20 Codenames: Pictures cards in a 5x4 grid.
3. Use `LOCK` before passing the device.
4. Tap `ALPHA` or `BRAVO` only when that player should see their keycard.
5. Copy the Session ID if you want to restore the same keycard later.
6. Use `AUD` only after the game is finished.

## Feedback

Please playtest and leave feedback:

- BGG thread: https://boardgamegeek.com/thread/3704610/house-rule-codenames-pictures-duet-hr-the-5x4-tigh
- Reddit thread: https://www.reddit.com/r/boardgames/comments/1t6di9p/i_just_made_house_rule_to_play_codenames_pictures/
- Instagram: https://www.instagram.com/hrxm/

Useful feedback:

- 7 or 8 tokens used
- Win or loss
- Agents remaining at the end
- Whether the loss felt fair or frustrating
- Any memorable clue or disaster

## References

- Codenames: Duet on BGG: https://boardgamegeek.com/boardgame/224037/codenames-duet
- Codenames: Pictures on BGG: https://boardgamegeek.com/boardgame/198773/codenames-pictures
- Codenames: Duet rulebook: https://czechgames.com/files/rules/codenames-duet-rules-en.pdf
- Codenames: Pictures rulebook: https://czechgames.com/files/rules/codenames-pictures-rules-en.pdf

## Deploy

This is static HTML/CSS/JS. You can deploy it with:

- GitHub Pages
- Netlify
- Vercel
- Any static file host

For GitHub Pages:

1. Create a new GitHub repository.
2. Upload `index.html` and `README.md`.
3. In repository settings, enable GitHub Pages from the main branch.

## Disclaimer

This is a non-commercial fan-made house rule and helper app. It is not affiliated with Czech Games Edition, Vlaada Chvatil, or the official Codenames line. Codenames and related marks belong to their respective owners.
# 5x4-keycard-app-for-codenames-pictures-duel-house-rule
