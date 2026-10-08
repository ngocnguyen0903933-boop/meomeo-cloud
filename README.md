# Meo Meo AI — Meo Cloud V0

Official public website and static cloud foundation for Meo Meo AI.

## Scope

This repository contains only public material:

- Product website and public documentation
- Project status and health metadata
- Public release metadata (no binaries are published yet)
- Static deployment workflow

Meo PC remains local-first and authoritative. See [`docs/architecture.md`](docs/architecture.md) and [`docs/data-boundary.md`](docs/data-boundary.md).

## Local preview

Serve this directory with any static HTTP server. No build step and no environment variables are required.

## Validation

The workflow in `.github/workflows/pages.yml` runs `node tools/validate.mjs` to check required files, internal public links, JSON syntax, CSP presence, and common secret patterns. Only an explicit public allowlist is staged in `_site`; tooling and repository documents are not deployed. This is a baseline check, not a guarantee that all possible secrets are detectable. Build metadata records the deployment timestamp and commit ID.

## Deployment

1. Push to `main`.
2. GitHub Actions validates the static tree.
3. The Pages artifact is deployed automatically.
4. GitHub Pages serves `meomeoai.mooo.com` using the repository `CNAME`.

DNS uses an A record from `meomeoai.mooo.com` to GitHub Pages (`185.199.108.153`) so MX records can coexist at the same hostname. Do not use a CNAME alongside MX. This is a GitHub hosting address, never the Owner's home IP. HTTPS must be enforced in repository Pages settings after certificate issuance and externally verified. Email is not considered ready until an actual inbound test is confirmed.

## Public endpoints

- `/health/` and `/api/health.json`
- `/status/` and `/api/status.json`
- `/releases/` and `/api/releases.json`
- `/api/version.json`
- `/docs/`

## Security

Do not commit credentials, private research, personal data, signing keys, private source, or device-control details. Report a security issue using [`SECURITY.md`](SECURITY.md).
