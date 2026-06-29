# Sawa Docs (Mintlify)

Canonical documentation for the Sawa platform — backend API, architecture, and mobile contract.

**Legacy Docusaurus docs (`SawaDocs/`) are deprecated.** Use this site instead.

## Local preview

```bash
npm i -g mint
cd MintlifyDocs
mint dev
```

Open http://localhost:3000

## Sync OpenAPI from backend

After API changes in `SawaApp`:

```bash
cd SawaApp
npm run docs:export:mintlify
```

This updates `openAPI.json` for the API Reference tab.

## Structure

- `en/` — English documentation (Diataxis: tutorials, explanation, how-to, reference)
- `ar/` — Arabic translations (core pages)
- `docs.json` — Navigation and branding
- `AGENTS.md` — Authoring guide for AI assistants

## Repository

Deployed from [Mintlify-Docs](https://github.com/Youssefrabei-dev/Mintlify-Docs) via Mintlify.
