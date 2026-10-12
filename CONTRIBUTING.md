# How we work

These rules apply to every repository in this organisation unless its own
`CONTRIBUTING.md` says otherwise.

## The flow
1. **Issue.** Every piece of work starts as one Issue (the *Task* template) on the
   organisation's project board.
2. **Branch.** `type/<issue>-<short-slug>`, where type is `feat`, `fix`, `chore` or
   `docs`, e.g. `feat/259-media-release-rule`.
3. **Commits and PR titles** follow [Conventional Commits](https://www.conventionalcommits.org):
   `feat(media): …`, `fix(ops): …`, `docs: …`. Where a repository runs the `PR title`
   check, a title that does not follow this fails it.
4. **Pull request.** One PR per Issue, "Closes #N" in the body, the template filled
   in. CI must pass.
5. **Merge.** Squash only. The owner's word approves a merge. Docs, chore and test
   PRs may auto-merge when CI is green.
6. **Deploy.** A merge to `main` deploys where the repository says so, then the
   deploy is read back. Each production deploy gets a GitHub Release with
   generated notes.

## Always
- No personal information about clients, owners or tenants in Issues, commits,
  logs or test data. Use record IDs.
- No passwords, keys or tokens anywhere in a repository.
- Live data changes, messages to staff and anything that spends money need the
  owner's yes first.
- Never merge on red or pending CI. Never force-push `main`.
- Canadian spelling.

## Decisions
Technical and design decisions are recorded as short ADRs in `docs/adr/`.
