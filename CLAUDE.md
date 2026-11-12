# CLAUDE.md

## Standing rules from John (every repo, every session, every machine)

### Questions and bugs: ANSWER and DIAGNOSE first, code only when John says so

1. When John asks a question, answer it. A question is not a request to change code.
2. When John points out a bug: diagnose it and find the cause, then tell him the cause and the fix you propose, and
   stop. Change code only after he says to. Before that: no edits, branches, worktrees, commits or deploys, even
   when the fix looks small or obvious. He may want it handed to another session instead.

Why: on 2026-11-12 a Mini session found an iOS cover-cache bug and started editing code straight away. John: "please
don't go code something immediately when I point out a bug. WE HAVE DISCUSED BEFORE. DIAGNOSE, then tell about fix,
then fix defect. Don't jump to code."

### Commits and pushes: check the credentials EVERY time, even in a brand-new repo

Wrong credentials once broke nearly every repo. Before any commit or push:

1. Git identity must be `John Hagewood <436715+hybernation@users.noreply.github.com>` for author AND committer.
   Set it on the commit itself (`GIT_AUTHOR_NAME`, `GIT_AUTHOR_EMAIL`, `GIT_COMMITTER_NAME`, `GIT_COMMITTER_EMAIL`),
   never by changing `git config`. Check before pushing:
   `git log -1 --format='%an <%ae> / %cn <%ce>'`.
2. GitHub account must be `hybernation` (`gh auth status`), with `origin` pointing at `github.com/hybernation/...`.
3. Follow this repo's own rule on `Co-Authored-By` / `Claude-Session` trailers. **the-77-experience-website and
   hybernation-software-website forbid them.**
4. **A brand-new repo** (no commits yet, or no remote): look at the identity and remote of John's other repos, then
   ASK John which GitHub account and git identity to use before the first commit. Never guess, never use a machine
   default.
5. If anything doesn't match, stop and tell John. Don't commit, push or "fix" credentials on your own.
