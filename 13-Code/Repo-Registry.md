# Repo Registry — every repository, one row

*The single roster of your codebases. An AI helping on any repo checks its row first — especially the licence and IP columns. Unknown stays blank, never guessed.*

| Repo | Where it lives | Stack | Licence | IP status | CI / tests | Status |
|---|---|---|---|---|---|---|
| *(example)* my-first-app | github.com/you/my-first-app | Python + Flask | MIT | Mine, clean | none yet | Active |
| | | | | | | |

**Column notes:**
- **Licence** — the repo's own licence. Blank means "not chosen yet", which is itself a flag.
- **IP status** — one of: *Mine, clean* · *Client-owned (see contract)* · *Employer risk — check* · *Mixed/unclear*. Anything but the first deserves a look before publishing or reusing code.
- **Status** — Active · Parked · Archived. Parked ~90+ days gets raised in a review, like any stream.
