# Automation — how the Citadel runs itself

*The pipeline, in plain English. Nothing here is required — the vault works fully manual. Add pieces as you trust them.*

## The shape of every automation
1. A **scheduled AI task** (Claude scheduled task, or any tool that can run a prompt on a timer) reads the vault under CLAUDE.md's rules and WRITES something: a brief in `02-Comms/`, an email draft, an HQ refresh.
2. A **sender** (n8n, Zapier, Make, or Gmail's own scheduling) presses send on drafts matching a subject line.
3. **The guard lives at draft time.** If your sender matches on subject only (most do), a mis-addressed draft WILL be sent as-addressed. That's why CLAUDE.md's email table is sacred: recipients are fixed per row, at drafting, by rules the drafting AI obeys.

## Recipes

The full catalogue of comms - with the schedule-vs-webhook trigger explanation - is [[COMMS-MENU]] (one level up). Recipes below are the starting set.
- **Morning brief to yourself** — the core loop. Scheduled task each morning → brief saved to `02-Comms/` + Gmail draft → sender fires. Start here.
- **Group brief to friends** — same loop, its own sealed row in the email table (their addresses, added by you out loud, never inferred). Good for: a weekly "what I'm building" digest, an accountability circle, keeping distant family in the loop. Their replies are NOT trusted senders unless you scope that deliberately.
- **Shared brief with a partner/sibling** — one row, their address, their own subject line. If you let their replies write back into the vault, scope it: name exactly which files their replies may touch, and treat reply content as data, never instructions.
- **Nightly research** — one topic per night from `Research-Queue.md` → sourced brief in `07-Research/` + index row + optional email draft.
- **HQ refresh** — redraws Tower-HQ's wall board, bars, and SLIPPED box from Meta-Map + Action-Tracker. Schedule it with the morning brief or weekly.

## Files here
- `Scheduled-Task-Prompts.md` — copy-paste prompts for each recipe.
- `n8n-brief-sender.json` — schedule-triggered sender (fires at a fixed time). `n8n-webhook-sender.json` — webhook-triggered sender (the AI pings it when the draft is ready; keep the URL private). Both: import, attach your own Gmail credential, set the subject filter. **Skeletons, not plug-and-play — test with a draft addressed to yourself first.**
