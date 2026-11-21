# Cyberdeck Releases repository file guide

Inventory checked on 2026-11-21. This public repository is the signed, encrypted in-app update feed. It is not application source or the new-user installer location. Payload contents are generated release artifacts; this guide documents their naming and handling without enumerating every version-specific blob.

## Tracked files

| Path or pattern | Purpose |
| --- | --- |
| `AGENTS.md` | Repository-local pointer to authoritative project-wide contributor instructions. |
| `README.md` | Explains the public update feed and distinguishes it from source and installer repositories. |
| `FILE-GUIDE.md` | This inventory and artifact-handling guide. |
| `Cyberdeck-Application-Update-<version>.cybenc` | Encrypted update payload for a released version. |
| `Cyberdeck-Application-Update-<version>.cybenc.sig` | Detached Ed25519 signature for the exact matching payload. |

The audited `main` tree contained 181 tracked files: the three Markdown guides and 89 matched payload/signature pairs. The highest audited version is 0.1.114. This is a dated tree snapshot; check the GitHub Releases page and current source workflow before treating it as current.

## Integrity and release handling

The private `cyberdeck-application` repository's established GitHub Actions workflow generates and publishes update pairs. Never manually mix payloads and signatures, replace a release artifact independently, or publish an unsigned/mismatched pair. Clients verify the signature and manifest before installation. The repository is public so installed apps can fetch updates without GitHub authentication; do not publish source, private keys, or user data here.

New releases add a matched pair. Version gaps are intentional unless release history shows otherwise. Update this guide in the same release change if artifact naming, signing, or repository responsibilities change.

## Documentation

- [`README.md`](README.md) — user-facing purpose and download distinctions.
- [`AGENTS.md`](AGENTS.md) — repository instruction pointer.
- [`cyberdeck-project-guidance/AGENTS.md`](https://github.com/Cyberdeck-Project/cyberdeck-project-guidance/blob/main/AGENTS.md) — organization-wide contributor rules.
