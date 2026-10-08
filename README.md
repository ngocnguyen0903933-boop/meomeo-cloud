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

The workflow in `.github/workflows/pages.yml` checks required files, internal links, JSON syntax, and sensitive-file patterns before deploying to GitHub Pages.

## Deployment

1. Push to `main`.
2. GitHub Actions validates the static tree.
3. The Pages artifact is deployed automatically.
4. GitHub Pages serves `meomeoai.mooo.com` using the repository `CNAME`.

DNS must contain a CNAME from `meomeoai.mooo.com` to `ngocnguyen0903933-boop.github.io`. HTTPS is enforced in repository Pages settings after certificate issuance.

## Public endpoints

- `/health/` and `/api/health.json`
- `/status/` and `/api/status.json`
- `/releases/` and `/api/releases.json`
- `/api/version.json`
- `/docs/`

## Security

Do not commit credentials, private research, personal data, signing keys, private source, or device-control details. Report a security issue using [`SECURITY.md`](SECURITY.md).

