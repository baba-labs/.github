# .github — organisation defaults

This repository supplies default community health files for every repository in the
`baba-labs` organisation. It is **public**: write everything here as if a prospective client
is reading it, and never mention unreleased products, clients or internal plans.

## How the defaults apply

- GitHub uses a file from here only when the repository has none of its own. It looks in the
  repository's `.github/`, then its root, then `docs/`, and falls back to this repository.
- The fallback happens when the page is rendered, so a change here applies immediately to
  every existing repository, not only new ones.
- **Not inherited:** `CODEOWNERS`, `dependabot.yml`, workflows and `LICENSE`. Each repository
  needs its own. Default files are also not included in clones.
- PR and issue templates only work from a public `.github` repository — keep it public.

## Layout

| Path                               | What it is                                                                                                |
| ---------------------------------- | --------------------------------------------------------------------------------------------------------- |
| `profile/README.md`                | Organisation profile shown on github.com/baba-labs, ending with the company registration disclosure       |
| `SECURITY.md`                      | Vulnerability reporting via `security@baba-labs.com`, with a safe harbour given by BaBa Labs Software Ltd |
| `CONTRIBUTING.md`                  | Workflow and Conventional Commits rules for all repositories                                              |
| `CODE_OF_CONDUCT.md`               | Reports to `conduct@baba-labs.com`; reports about the director go to GitHub's own reporting tools         |
| `SUPPORT.md`                       | Where to ask for help                                                                                     |
| `.github/PULL_REQUEST_TEMPLATE.md` | Default PR template (emoji headings, Jira/ADR/requirement links, checklist)                               |
| `.github/ISSUE_TEMPLATE/`          | Issue forms (`bug_report.yml`, `documentation.yml`) and `config.yml`                                      |

## Rules for changes

- The legal entity is **BaBa Labs Software Ltd**; the trading name is **BaBa Labs**. Use the
  legal name only in the profile disclosure and the security safe harbour.
- The company has a single director. Don't write text that assumes a second person to
  escalate to.
- Keep the `PROJ-000` placeholder in the PR template generic. Never put a real Jira project
  key in it — the file is public.
- A change here changes every repository's templates at once. Say so in the PR if a template
  loses or renames a section people rely on.
- Plain, direct British English. No marketing tone in policy documents.
