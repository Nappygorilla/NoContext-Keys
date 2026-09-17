# NoContext-Keys

This repository is the public license index used by the NoContext software key checker.

## Sections

- `keys/3-day.json` — active 3-day licenses
- `keys/1-week.json` — active 1-week licenses
- `keys/lifetime.json` — active lifetime licenses
- `keys/index.json` — section metadata and counts

## Key format

Because this repository is public, it does **not** contain plaintext license keys. Each entry contains the SHA-256 hash of the license key plus its product, creation time, expiration time, and status.

The software key checker should SHA-256 the key entered by the user and look for that hash in the appropriate section. A key is valid only when its `status` is `active` and its `expiresAt` is still in the future. Expired 3-day and 1-week entries are removed from the repository during synchronization. Lifetime entries remain until they are deactivated.

The NoContext backend is responsible for keeping these files synchronized with the license records in the NoContext database.
