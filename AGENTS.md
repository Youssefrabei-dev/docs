# Sawa Docs — Agent authoring guide

## Structure (Diataxis)

| Quadrant | Folder | Purpose |
|----------|--------|---------|
| Tutorials | `en/tutorials/` | Linear learning paths for new devs |
| Explanation | `en/explanation/` | Architecture, concepts, diagrams |
| How-to | `en/how-to/` | Task-oriented guides |
| Reference | `en/reference/` | Facts: env vars, domains, scripts |

## Conventions

- Every page needs `title` and `description` in frontmatter.
- Internal links: root-relative, no extension (`/en/explanation/auth-architecture`).
- Use Mermaid for diagrams; store images in `images/`.
- Auth docs must reference **Better Auth** (`/api/auth/*`), not legacy JWT.
- API shapes live in the **API Reference** tab; domain pages link to OpenAPI tags.

## OpenAPI sync

From `SawaApp/`:

```bash
npm run docs:export:mintlify
```

Writes `../MintlifyDocs/openAPI.json`. Run before publishing doc changes that depend on API surface.

## Adding a page

1. Create `en/<section>/<slug>.mdx`
2. Add path to `docs.json` navigation
3. Cross-link from related explanation/reference pages

## Source of truth

- Backend behavior: `SawaApp/`
- Legacy content (deprecated): `SawaDocs/` — port only, do not link as canonical
