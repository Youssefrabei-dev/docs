# Sawa documentation — contributor guide

## About this project

- Canonical backend documentation for **Sawa** lives in this Mintlify site (`MintlifyDocs`).
- Legacy Docusaurus docs in `SawaDocs` are migration source material only — verify against `SawaApp` before porting.
- Runtime behavior source of truth: `SawaApp` (Express, Better Auth, Drizzle, generated OpenAPI).

## Repositories

| Repo | Role |
| --- | --- |
| `SawaApp` | Backend API, schema, auth, OpenAPI generation |
| `MintlifyDocs` | This documentation site |
| `SawaDocs` | Legacy docs (deprecated after parity) |

## Source-of-truth files

Before changing docs, read:

- `SawaApp/api/server.ts` — middleware order, route mounting, public paths
- `SawaApp/api/config.ts` + `SawaApp/.env.template` — environment variables
- `SawaApp/docs/auth/better-auth-integration.md` — current auth (not legacy JWT docs)
- `SawaApp/api/docs/` + `SawaApp/api/docs/registry.ts` — OpenAPI generation
- `SawaApp/api/contract/` — mobile/CI contract API

## Information architecture (Diataxis)

| Nav group | Diataxis type | Purpose |
| --- | --- | --- |
| Start here | Mixed | Orientation and checklists |
| Tutorials | Tutorial | Linear learning paths |
| Concepts | Explanation | Architecture and design |
| How-to guides | How-to | Task-focused procedures |
| Reference | Reference | Lookup tables and facts |
| API Reference | Reference | Auto-generated from `openAPI.json` |

Do not hand-write endpoint reference pages when OpenAPI already documents them.

## OpenAPI sync

After changing routes, DTOs, or `registerPath` metadata:

```bash
cd SawaApp
npm run docs:export:mintlify
```

This writes `MintlifyDocs/openAPI.json`. Commit the updated spec with related doc changes.

## Page conventions

- File names: kebab-case (`request-lifecycle.mdx`)
- Frontmatter: `title`, `description`, optional `keywords`
- Internal links: root-relative, no file extensions (`/en/concepts/architecture/authentication`)
- Code blocks: always include a language tag
- Auth docs: Better Auth only — never document JWT refresh, `/auth/local/*`, or `JWT_SECRET` as current

## Mintlify tooling

- Local preview: `mint dev` (from repo root)
- Link check: `mint broken-links`
- Mintlify skill: `npx skills add https://mintlify.com/docs`

## Migration status

English backend docs ship first. Arabic, Mobile, and UX sections are placeholders until backend docs stabilize.
