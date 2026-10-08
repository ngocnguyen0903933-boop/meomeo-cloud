# Release metadata contract

Public release data is exposed by `/api/version.json` and `/api/releases.json`.

Reserved fields support later signed-update work:

- `signature`
- `signerId`
- `provenance`
- `immutableVersionId`

These fields are currently `null` where appropriate. Signed updates remain off until a separate trust and secret-management foundation is reviewed and approved. Production private keys must never be stored in this repository.

