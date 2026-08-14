# 02-Comms — everything that talks

The hub for every message the Citadel produces or schedules. The full catalogue of what's possible lives in [[COMMS-MENU]] — read that first. The machinery (scheduled-task prompts, n8n workflows, webhooks) lives in `Workflows/`.

- `Daily/` — morning briefs land here as `YYYY-MM-DD-Brief.md` (plus weekly pulses).
- `Research/` — the email-facing copies of research briefs (the canonical research files stay in `07-Research/`, indexed).
- `Outreach/` — digests and check-ins to other people: friends, family, an accountability buddy. Copies of what was sent, dated.
- `Workflows/` — the plumbing: `AUTOMATION.md`, `Scheduled-Task-Prompts.md`, n8n workflow files.

**The one rule that rules them all:** every outgoing comm is either on its own sealed row of CLAUDE.md's auto-send table, or it queues in `06-Logistics/Outbox.md` and waits for the owner's yes. There is no third path.
