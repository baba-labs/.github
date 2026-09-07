# Contributing

These are the working conventions for every repository owned by baba-labs. Most of our
repositories are private and worked on by a small team; this document exists so the
conventions are written down rather than remembered, and so anyone joining — or any
customer's auditor asking how we work — gets a straight answer.

## Before you start

- Work is tracked in Jira. Every change should trace to an issue.
- Discuss anything architectural before building it. A decision worth arguing about is
  worth an ADR in the relevant repository's `docs/adr/`.
- If you are about to spend more than a day on something you are not sure about, that is
  a spike. Time-box it and write down the answer.

## Branching

Trunk-based. `main` is always releasable.

- Branch from `main`, keep it short-lived, and rebase rather than merge `main` into it.
- Squash merge. One commit per pull request on `main`.
- Never force-push `main` or `support/*`.
- Hotfixes are fixed forward on `main` and cherry-picked to `support/x.y` — never the
  other way round, which is how a fix gets lost at the next release.

## Commits

[Conventional Commits](https://www.conventionalcommits.org/). This is enforced by a
required check, and release automation depends on it.

```text
<type>(<optional scope>): <description>

[optional body]

[optional footer]
```

Types: `feat`, `fix`, `docs`, `style`, `refactor`, `perf`, `test`, `build`, `ci`, `chore`, `revert`.

A breaking change is marked with `!` after the type, or a `BREAKING CHANGE:` footer.
Both trigger a major version bump, so use them deliberately.

```text
feat(audit): record policy version on every event
fix(worker): renew lock before the five-minute maximum
feat(api)!: require justification on all mutation requests
```

Write the description as what the change does, not what you did. `fix(worker): renew
lock before expiry` is useful; `fixed bug` is not.

## Pull requests

- One logical change per pull request. If the description needs the word "also", split it.
- Fill in the template. It is short on purpose.
- All checks green before review. A red pull request is not ready, and asking someone to
  review around a failure wastes their time twice.
- Draft pull requests are welcome and encouraged for early feedback.

### Review

- Review for correctness, security, and whether the next person will understand it.
- Say what is required to change and what is a suggestion. "Consider…" and "This needs
  to change before merge" are different, and reviewers should make clear which they mean.
- Approving means you would be comfortable being paged for it.

## Quality gates

Every repository runs the same gates through
[`baba-labs/pipeline-templates`](https://github.com/baba-labs/pipeline-templates):

- Build with warnings as errors
- Unit and component tests
- Static analysis with a quality gate on new code
- Dependency and secret scanning
- Infrastructure-as-code lint where applicable

Gates apply to **new code**. Existing code is not held to a standard retroactively, but
nothing new should make the position worse.

If a gate is wrong, fix the gate — in the open, with a pull request explaining why.
Do not add a suppression to get a change through and plan to revisit it.

## Tests

Write the test at the cheapest level that would actually catch the failure. A unit test
that mocks the thing being tested proves nothing; an end-to-end test for a pure function
is slow for no reason.

Each repository's `docs/testing.md` defines its test tiers and what belongs in each.

## Secrets

Never commit credentials, keys, certificates or connection strings — including in test
fixtures, example configuration, or a commented-out line.

Every repository ignores `*.pem`, `*.key`, `*.p12`, `*.pfx` and `.local-only/` by
default. Push protection is enabled. If you believe you have committed a secret, say so
immediately: rotating a key is routine, and discovering it later is not.

## Documentation

Change the documentation in the same pull request as the code. Documentation in a
follow-up is documentation that does not happen.

Deeper engineering standards live in `baba-labs/engineering-standards`.
