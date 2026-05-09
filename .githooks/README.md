# PeopleSpaceAM Git Hooks

These hooks are organization defaults. They do not apply automatically to product repositories.

To use them in a repo:

```bash
cp -R /path/to/peoplespaceam-dotgithub/.githooks <repo>/.githooks
cd <repo>
git config core.hooksPath .githooks
chmod +x .githooks/*
```

Recommended policy:

- Commit `.githooks/` in each repo that opts in.
- Keep hooks lightweight and dependency-free.
- Put expensive tests in CI, not in hooks.
- Use `SKIP_GITHOOKS=1` only for emergency bypasses and document why in the PR.

Available hooks:

- `pre-commit`: blocks commits on protected branches, unresolved conflicts, likely secrets, oversized staged files, and trailing whitespace in common text files.
- `commit-msg`: requires issue references in normal commits.
- `pre-push`: blocks direct pushes to protected branches and optionally runs local checks when `RUN_LOCAL_CHECKS=1`.
