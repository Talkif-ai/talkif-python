# CLAUDE.md — talkif-python

## What this repo is

The public, **generated** Python SDK for the Talkif API, published to PyPI (talkif). It is
one of two SDK repos (`Talkif-ai/talkif-node`, `Talkif-ai/talkif-python`).

The source of truth is NOT here. It is `Talkif-ai/web` → `fern/`:
`openapi.json` (curated public spec, synced from backend-rs), `overlays.yml`
(docs/SDK-only adjustments) and `generators.yml` (this SDK's generator config).
Fern regenerates this repo from that folder and opens a pull request here.

## Rules

- **Do not hand-edit generated code.** It is overwritten on the next
  regeneration. If a method name, type, pagination or default is wrong, fix it
  upstream: the OpenAPI annotation in `backend-rs` (preferred) or
  `web/fern/overlays.yml`.
- **Hand-written files must be listed in `.fernignore`** or Fern deletes them.
  Keep that list minimal: README, LICENSE, this file, release workflow, and any
  wrapper/helper code in a clearly named directory.
- **This repo is public.** Never commit internal service names (backend-rs,
  catflow), NATS subjects, infra details, ops identifiers, or unreleased
  endpoints. Public API surface only. Same rule as `Talkif-ai/webrtc-js`.
- **Brand:** Talkif / Talkif-ai. Never the retired alternate spelling.
- **No secrets.** Publishing uses trusted publishing (OIDC) from GitHub Actions;
  there is nothing to paste.

## Release

Releases are **tag-driven**, same as `webrtc-js`:
1. A Fern regeneration PR lands (`fern-api[bot]`). Review the diff — it is the
   public contract changing.
2. Merge. Tag `vX.Y.Z` and push the tag. GitHub Actions builds, tests and
   publishes to PyPI (talkif) with provenance. Pushing `main` never publishes.
3. Semver: additive endpoints/fields → minor; removed or renamed → major.

Do not publish a version whose endpoints are not live on `api.talkif.ai` yet.

## Conventions

- Semantic commits (`feat:`, `fix:`, `chore:`). No attribution trailers.
- Bugs in generated output that are Fern's fault get an issue in
  `fern-api/fern`, linked from an issue here.
