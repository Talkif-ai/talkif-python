# Changelog

All notable changes to `talkif` are documented here. The SDK is generated from the
public Talkif API definition; see the [API reference](https://docs.talkif.ai) for details.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and this
project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html). While the
version is below 1.0.0, a minor release may contain breaking changes; they are listed under
**Removed** or **Changed**.

## [Unreleased]

## [0.2.0] — 2026-10-02

### Added

- `transfers`: transfer destinations and destination groups (`create_destination`, `list_destinations`, …, `create_group`, `list_groups`, …), testing an
  app destination and rotating its signing secret, its delivery log, accepting or declining
  transfer offers (`accept_offer`, `decline_offer`, `get_offer`), and member tags, available hours and availability
  (`list_members`, `set_member_tags`, `set_member_hours`, `set_member_availability`, …).
- `accounts`: `get_roles()` and `get_permissions()`.
- `calls`: `calls.list_calls()` — one paginated list of calls, filterable by status.
- `public_calls`: `public_calls.create_call()`, `get_call_status()`, `relay_offer()` and `end_call()` use the documented `/public/calls` paths.

### Removed

- `calls`: `calls.get_active_calls()` and `calls.get_call_history()` are replaced by `calls.list_calls()`. The endpoints still answer, so 0.1.x keeps
  working, but they are no longer part of the SDK.

## [0.1.1] — 2026-09-12

### Changed

- List methods for billing, calls and voice agents take `limit`/`offset` and return typed
  list responses.

### Fixed

- Auto-pagination starts at the first item instead of skipping it.

## [0.1.0] — 2026-09-12

### Added

- First release: calls, public (embedded) calls, voice agents and their functions and
  templates, phone numbers and providers, contacts, do-not-call, campaigns, schedules,
  billing, analytics, models and error codes.

[Unreleased]: https://github.com/Talkif-ai/talkif-python/compare/v0.2.0...HEAD
[0.2.0]: https://github.com/Talkif-ai/talkif-python/compare/v0.1.1...v0.2.0
[0.1.1]: https://github.com/Talkif-ai/talkif-python/compare/v0.1.0...v0.1.1
[0.1.0]: https://github.com/Talkif-ai/talkif-python/releases/tag/v0.1.0
