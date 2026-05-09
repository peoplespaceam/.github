# PeopleSpaceAM Organization Defaults

Organization-wide community health files, issue templates, hook templates, and shared GitHub Actions workflows.

## Issue Templates

Default issue templates live in `.github/ISSUE_TEMPLATE`.

These apply to PeopleSpaceAM repositories that do not define their own `.github/ISSUE_TEMPLATE` directory.

## Reusable Workflows

Reusable workflows live in `.github/workflows`:

- `reusable-ci.yml`
- `reusable-publish-image.yml`

Call them from a product repo:

```yaml
jobs:
  ci:
    uses: peoplespaceam/.github/.github/workflows/reusable-ci.yml@main
```

## Workflow Templates

Starter workflow templates live in `.github/workflow-templates`:

- `peoplespaceam-ci.yml`
- `peoplespaceam-publish-image.yml`

Use these from the GitHub Actions "New workflow" screen.

## Git Hooks

Hook templates live in `.githooks`.

They are not applied automatically. A product repo opts in with:

```bash
cp -R /path/to/peoplespaceam-dotgithub/.githooks <repo>/.githooks
cd <repo>
git config core.hooksPath .githooks
chmod +x .githooks/*
```
