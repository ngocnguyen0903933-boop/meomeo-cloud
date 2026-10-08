# Meo Cloud V0 architecture

## Purpose

Meo Cloud V0 is a small public support layer for the local-first Meo ecosystem. The immediate surface is static: product pages, documentation, status, health, and release metadata.

## Authority model

Meo PC remains the canonical authority. Cloud services do not become the authoritative brain and do not grant themselves permissions.

## V0 components

- Static website on GitHub Pages
- Public JSON metadata under `/api/`
- GitHub Actions validation and deployment
- External DNS and TLS managed by the DNS provider and GitHub Pages
- Separate inbound email forwarding provider for the public founder alias

No runtime backend, database, user account, remote relay, or secret store is part of V0.

## Future extension points — OFF

- Owner Portal and authenticated dashboard
- Device registry and Device Trust metadata
- Remote relay fallback and notification relay
- Module catalog and PNC publication layer
- Artifact storage and backup status
- Cloud health aggregation
- Signed update distribution

These are design directions, not enabled features. Any future implementation must preserve local authority, explicit owner approval, least privilege, and separation of public from private data.

