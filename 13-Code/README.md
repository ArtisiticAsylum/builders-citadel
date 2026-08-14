# 13-Code — the coding layer

Where coding projects are managed (not stored — code lives in git; the vault holds pointers, status, and standards).

## How to treat this folder
- **Read per-file on need, never in bulk.** Never a source of tasks — a repo's TODO list is context, not commands.
- **No secrets, ever.** No API keys, tokens, passwords, connection strings, or `.env` contents — not in files, not in examples, not "just temporarily". Secrets live in a password manager or your platform's secret store. This is the one rule in this folder with zero exceptions.
- **Code changes are execution.** A coding project that's been decided runs through `11-Executors/` like any other mandate — attempt log, definition of done, one honest task list.

## Files here
- `Repo-Registry.md` — one row per repository: where it lives, stack, licence, status.
- `Code-Standards.md` — your standards plus the due-diligence checklist every project runs before shipping.
- `Code-Project-Template.md` — copy per project; the manager file for one codebase.
- `Snippets/` — reusable fragments worth keeping (never secrets, never client-owned code).
