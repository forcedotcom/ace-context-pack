# Contributing to ACE Context Packs

## Governance model: Salesforce maintained

Salesforce writes and maintains every pack in this repository. Only Salesforce employees on the maintainer team have write access, and they are the final arbiters of what is published.

**We don't accept outside pull requests.** Pull requests from outside the maintainer team are closed with a pointer to Issues.

## Issues, requests & ideas

Use [GitHub Issues](https://github.com/forcedotcom/ace-context-pack/issues/new/choose) to:

- report a pack that is wrong, unclear or out of date
- request a pack for a use case we don't cover yet

Don't include customer data, org IDs, credentials or other private details in an issue. Report security issues as described in [SECURITY.md](SECURITY.md).

## For maintainers: adding or updating a pack

1. Copy [`templates/PACK.md`](templates/PACK.md) to `packs/<industry>/<pack>/PACK.md`. Folder names are kebab-case.
2. Fill in the frontmatter (rules below) and the body. Put supporting files in `references/` as `.md` and link them with relative links.
3. Add or update the pack's row in the [README catalog](README.md#catalog), linked to `packs/<industry>/<pack>/`.
4. Add a line to [CHANGELOG.md](CHANGELOG.md).
5. Open a pull request. It needs one CODEOWNERS approval.

Updating a pack means editing it in place: `main` always holds the latest version. Bump `metadata.lastUpdated` on every change.

### Frontmatter

```yaml
---
name: <industry>-<pack>
description: One line, up to 1024 characters, on what the pack covers and when to use it.
metadata:
  industry: <industry>
  status: published
  lastUpdated: YYYY-MM-DD
---
```

| Field | Rule |
|---|---|
| `name` | Exactly `<industry>-<pack>`, matching the folders |
| `description` | Required, one line, max 1024 characters |
| `metadata.industry` | Matches the industry folder |
| `metadata.status` | `published` or `deprecated` |
| `metadata.lastUpdated` | `YYYY-MM-DD` |

No other keys are allowed. Every value fits on one line (no `>` or `|` blocks).

### Content rules (checked by the reviewer before approval)

- Markdown only: `PACK.md` plus `references/**/*.md`
- Each file is at most 256 KB
- No SQL: no `sql` code blocks and no `SELECT … FROM` statements
- No email addresses, Salesforce org IDs, internal or org-specific hostnames, or credentials
- Relative links resolve to files in this repo
- Every pack is linked from the README catalog

## Code of Conduct

Please follow our [Code of Conduct](CODE_OF_CONDUCT.md).

## License

Content in this repository is licensed under [CC BY-NC 4.0](LICENSE.txt).
