# Personalise Checklist — before you publish YOUR version

*You don't need this file just to USE the Citadel — `SETUP.md` handles that. This checklist is for anyone (including the original author) about to publish a fork or copy of this repo publicly. Work through it top to bottom so no personal detail ever leaks.*

## The must-change list

1. **`CLAUDE.md` — the owner line and the email auto-send table.** Replace the example addresses with your own (or leave the table as the example placeholders if you're publishing a clean template). No real address of yours — or anyone else's — should ship in a public repo.
2. **`.github/FUNDING.yml` — the Sponsor button.** Put in your own donation handle, or leave every line commented out (no button appears), or delete the file.
3. **`LICENSE` — the copyright line.** If you're republishing a substantially modified version, add your name alongside or per the license terms. Keep the original attribution.
4. **`README.md` — the "Support this" section.** Your handle, your wording.
5. **`SETUP.md` and `GUIDE.md` — the creator intro ("Hey, I'm Aye").** If you're republishing your own flavour, either keep the intro as credit to the original or replace it with your own story — just don't leave a mix of two people's voices.
6. **`GUIDE.md` screenshots.** Any screenshots you add must come from a CLEAN vault or be scrubbed: check every image for real email addresses, real names, private file names, and anything in an `_` folder.

## The must-remove list

- **Build scaffolding:** any `HANDOFF.md` or working notes from building your version.
- **Log residue:** entries in `06-Logistics/Session-Log/` and `06-Logistics/Usage-Log.md` from your private use — a published template ships with empty logs.
- **Filled personal files:** `03-DNA/North-Star.md` and friends must be back to their blank-template state; `05-People/` must be empty of real people.

## The never-ever list

- No real email addresses anywhere (search the repo for `@` before publishing).
- No secrets, API keys, tokens, or passwords — the vault rule is "password manager only", and that applies doubly to a public repo.
- No content from `_` (restricted) folders — if it was private in the vault, it does not exist to the public repo.

*Quick final check: search the whole repo for your own name, your email domains, and `@`. Five minutes here saves a very bad day later.*
