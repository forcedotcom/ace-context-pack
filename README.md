# ACE Context Packs

Out-of-the-box context packs for Salesforce Data 360 ACE, written and maintained by Salesforce.

Browse the catalog, find the pack for your use case, and copy it. Nothing to install.

## What's a context pack

A context pack is a folder of Markdown files that describes the business context for one industry use case:

- `PACK.md`: the pack itself, with a short frontmatter header (name, description, industry, status, last updated)
- `references/`: optional supporting Markdown that `PACK.md` links to

Review each pack and adapt it to your business before you use it.

## Catalog

| Pack | Industry | Description | Status |
|---|---|---|---|
| _No packs published yet._ | | | |

<!-- Add one row per pack, linked to its folder, e.g.
| [retail-orders](packs/retail/orders/) | Retail | Order lookup, status and returns | published |
-->

## How to copy a pack

`main` always holds the latest version of every pack.

**One file, in the browser:** open the pack folder, open `PACK.md`, and use **Copy raw file** (or **Raw**).

**One file, from a terminal:**

```bash
curl -O https://raw.githubusercontent.com/forcedotcom/ace-context-pack/main/packs/<industry>/<pack>/PACK.md
```

**One pack with its references:**

```bash
git clone --depth 1 --filter=blob:none --sparse https://github.com/forcedotcom/ace-context-pack.git
cd ace-context-pack
git sparse-checkout set packs/<industry>/<pack>
```

**Everything:**

```bash
git clone --depth 1 https://github.com/forcedotcom/ace-context-pack.git
```

## Repository layout

```
packs/
└── <industry>/
    └── <pack>/
        ├── PACK.md
        └── references/      (optional)
            └── *.md
```

## What changed

See [CHANGELOG.md](CHANGELOG.md). Older versions of a pack are in the git history.

## Feedback

Found something wrong, unclear or out of date? [Open an issue](https://github.com/forcedotcom/ace-context-pack/issues/new/choose).
This repository is maintained by Salesforce and does not accept outside pull requests. See [CONTRIBUTING.md](CONTRIBUTING.md).

## Security

Report security issues as described in [SECURITY.md](SECURITY.md). Don't open a public issue.

## License

Licensed under [Creative Commons Attribution-NonCommercial 4.0 International (CC BY-NC 4.0)](LICENSE.txt).
