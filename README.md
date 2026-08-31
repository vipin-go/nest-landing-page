# Gabriel Operator — landing-page-builder skill pack

Canonical skill scaffold for a Persona's **Git-backed marketing landing page**:
`assets/landing-page.json`, a validation script, and authoring guides.

Published from **[go-code-bot/landing-page-builder](https://github.com/go-code-bot/landing-page-builder)**.

## Install

```bash
npx github:go-code-bot/landing-page-builder
npx github:go-code-bot/landing-page-builder add ./my-landing-page
npx github:go-code-bot/landing-page-builder sync ./my-landing-page
```

Or:

```bash
curl -fsSL https://raw.githubusercontent.com/go-code-bot/landing-page-builder/main/install.sh | bash
curl -fsSL https://raw.githubusercontent.com/go-code-bot/landing-page-builder/main/install.sh | bash -s -- ./my-landing-page
```

## What gets installed

```text
SKILL.md
gabriel.workspace.json
assets/landing-page.json
references/landing-page-contract.json
scripts/validate-landing-page.js
```

`assets/landing-page.json` is the canonical portable schema-v2 definition. It
stores a stable `resourceKey` and the landing page copy (headline,
subheadline, feature highlights, call-to-action label). It must not store
environment-local page, user, or collection IDs.

In a Persona workspace, this repo is submoduled at
`references/landing-pages/<resource-key>/`. Unlike List/Pipeline/Workflow,
there is no automated import step yet — after editing, also copy the
`landingPage` object into the parent persona's own
`assets/chat-config.json` under `publishedConfig.landingPage` and push both.
See `SKILL.md` → **Getting content live** for the full explanation.

## Validate

```bash
node scripts/validate-landing-page.js assets/landing-page.json
```
