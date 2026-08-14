# Code Standards & Due-Diligence Checklist

*Your house rules for any code an AI writes or reviews with you, plus the checklist that runs before anything ships. Edit the standards to taste; the checklist's first item is not negotiable.*

## Standards (starter set — make them yours)
- Plain-English comments for anything non-obvious; future-you is the audience.
- Small commits with honest messages; no "misc fixes".
- A README in every repo: what it is, how to run it, how to test it.
- Prefer boring, maintained dependencies over clever, abandoned ones.
- AI-written code gets the same review as human code — line by line, before it merges.

## Due-diligence checklist (before any release, publish, or hand-off)
1. **Secrets sweep — always first.** Search the repo for keys, tokens, passwords, `.env` files, and hard-coded credentials — including in git history if the repo was ever private. One leaked key outweighs every other item on this list.
2. **Dependency licences.** List every dependency's licence; confirm they're compatible with the repo's own licence and its intended use (commercial use changes the answer).
3. **IP check.** Does anything in here belong to a client or employer, or come from a contract with strings? Check the repo's row in `Repo-Registry.md` — if IP status isn't *Mine, clean*, resolve before publishing.
4. **Security review.** Inputs validated, no injection paths, auth on anything that needs it, dependencies not flagged for known vulnerabilities. For anything handling other people's data, do this pass with fresh eyes or a second opinion.
5. **Definition of done met.** Whatever the project's `Code-Project-Template.md` file says "done" means — tests pass, docs updated, deployed where it should be. Done is a checklist, not a feeling.

*A failed item isn't shame, it's the system working. Fix, re-run, then ship.*
