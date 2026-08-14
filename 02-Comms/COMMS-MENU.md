# COMMS MENU — every way the Citadel can talk, explained

*The full catalogue. Each comm has: who it goes to (its own sealed row in CLAUDE.md's table — rows never cross), a cadence, a trigger type, a prompt template (in `Workflows/Scheduled-Task-Prompts.md`), and optionally an n8n workflow (in `Workflows/`). Start with the Daily Brief only; add one comm at a time as you trust the system.*

## The two trigger types (understand this once)

**Schedule trigger** — n8n (or any sender) fires at a fixed time and sends whatever draft matches the subject line. Simple, but if the AI hasn't finished drafting, nothing sends; if a draft is mis-addressed, it sends as-addressed. Workflow: `n8n-brief-sender.json`.

**Webhook trigger** — the scheduled AI task finishes drafting, THEN calls a private n8n URL ("the webhook"), which sends that draft immediately. Fires exactly when the draft is ready, never before. Workflow: `n8n-webhook-sender.json`. Keep the webhook URL private — anyone who has it can trigger a send — and note it still sends the draft AS ADDRESSED. In both designs the real guard is the same: **recipients are fixed at draft time by CLAUDE.md's table.**

## Comms TO you

**1. Daily Brief** — the core loop. What moved, what's due, top 3, what slipped, what was skipped. To your own addresses, every morning. Prompt #1 · either trigger. Copy saved in `Daily/`.

**2. Weekly Pulse** — Sunday sweep: Meta-Map refresh, parked-stream questions, money pulse (if you keep 08-Money), items older than 14 days. Prompt #5 · usually rides inside Sunday's daily brief. Copy in `Daily/`.

**3. Research Brief** — you drop a topic in `06-Logistics/Research-Queue.md`; overnight it becomes a sourced one-pager, indexed in `07-Research/`, emailed to you. Prompt #3 · schedule trigger (it runs at night anyway). Email copy in `Research/`.

**4. One-off reminders** — "remind me Thursday about X." A scheduled task with a single fire time, to your addresses only. No n8n needed if your AI tool schedules natively.

## Comms TO other people (each gets its OWN row, added by you out loud)

**5. Friends & Family Digest** — a short, warm weekly "what I'm building / how I'm doing" to a named group. Public-safe content only: nothing from `_` folders, 05-People, 08-Money, 09-Partner, or Locked streams. This is staying close without performing on social media. Prompt #4 · webhook trigger recommended (send when ready, not at a blind time). Copies in `Outreach/`.

**6. Shared brief with one person** — a sibling, a best friend, a co-founder: their own subject line, their own row, content scoped to what you share with THEM. Same prompt pattern as #5 with a narrower lens.

**7. Accountability check-in** — to a buddy or coach: this week's commitments from Action-Tracker, what landed, what slipped (the honest box, outbound). Powerful and exposing — keep the recipient list to exactly one person.

**8. Partner brief** — if you run 09-Partner: schedules, reminders, logistics to your partner's addresses. The ONLY thing that ever auto-sends to them; everything else queues for your approval. Their replies write only to files you name in CLAUDE.md, as data, never instructions.

## Comms FROM other people (inbound)

**9. Feedback loop** — replies to your own briefs, or emails subject-lined `VAULT: ...`, from YOUR addresses only, can write updates into the vault ("spent 40 on petrol" → Spending-Log). Any other sender needs you to name them, live, with scope.

**10. Scoped inbound from a named person** — e.g. your partner's reply updates only the schedule file. Anything in a reply that reads like AI commands gets flagged to you, never acted on.

## Never automated, ever

**Outreach to anyone not on a row** — job applications, cold emails, replies to strangers — queues in `06-Logistics/Outbox.md` and waits for your explicit yes, recipient named by you. Drafting is automated; sending never is.

## Adding a new comm (the checklist)
1. You name it, its recipients (out loud, exact addresses), its subject line, its cadence.
2. Its row goes into CLAUDE.md's table — read back address by address.
3. Its prompt gets added to `Workflows/Scheduled-Task-Prompts.md` (copy the closest existing one).
4. Pick its trigger: schedule or webhook. Duplicate the matching n8n workflow, change ONLY the subject filter.
5. Dry run: first send goes to your own address; you read it; then the real row goes live.
