# .github

Organisation-wide defaults for every repository owned by **baba-labs**.

GitHub resolves these files as a fallback: when a repository has no file of a given
type, the version here is used instead. That lookup happens when the file is needed,
not when a repository is created — so changes here take effect immediately across
existing and new repositories alike.

## Resolution order

For any given file, GitHub checks:

1. The repository's own `.github/` folder
2. The repository root
3. The repository's `docs/` folder
4. **This repository**

First match wins. A repository that needs to differ simply adds its own file.

## What lives here

| File | Applies to |
|---|---|
| `profile/README.md` | The organisation profile page at github.com/baba-labs |
| `CODE_OF_CONDUCT.md` | All repositories |
| `CONTRIBUTING.md` | All repositories |
| `SECURITY.md` | All repositories — vulnerability disclosure policy |
| `SUPPORT.md` | All repositories — where to get help |
| `.github/PULL_REQUEST_TEMPLATE.md` | All repositories |
| `.github/ISSUE_TEMPLATE/` | All repositories |

## What does NOT inherit

These must exist in each repository individually. Putting them here does nothing:

- `CODEOWNERS`
- `dependabot.yml`
- Workflows — shared workflows are referenced from
  [`baba-labs/pipeline-templates`](https://github.com/baba-labs/pipeline-templates) via `uses:`
- `LICENSE`

## Two things to remember

**This repository is public.** It has to be — GitHub does not support private
`.github` repositories for organisation defaults, and issue and pull request
templates require public specifically. Nothing internal or sensitive belongs here.

**Default files are not included in clones or downloads.** They render in the GitHub
UI only. If a document must exist inside a checkout — something an auditor expects to
find in the repository itself — it has to live in that repository.
