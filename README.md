# Sawa Docs (Mintlify)

Canonical backend documentation for the Sawa API. Built with [Mintlify](https://mintlify.com).

## Related repositories

- **SawaApp** — Express API, Drizzle schema, Better Auth, OpenAPI generation
- **SawaDocs** — Legacy Docusaurus docs (deprecated after migration parity)

## Local development

Install the Mintlify CLI:

```bash
npm i -g mint
```

Preview docs from this directory:

```bash
mint dev
```

Open `http://localhost:3000`.

## Sync OpenAPI from the backend

After changing routes or DTOs in `SawaApp`:

```bash
cd ../SawaApp
npm run docs:export:mintlify
```

This updates `openAPI.json` for the API Reference tab.

## Contributing

See [AGENTS.md](./AGENTS.md) for source-of-truth rules, Diataxis structure, and page conventions.

## Publishing

Push to the default branch after connecting the Mintlify GitHub app from your [dashboard](https://dashboard.mintlify.com).
