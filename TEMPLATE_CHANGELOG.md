# Template Changelog

## 2026-04-01

- Fixed: Claude Code adapter fails with `--dangerously-skip-permissions cannot be used with root/sudo privileges` (#4)
  - Replaced `gosu` with `setpriv --inh-caps=-all` in entrypoint to fully drop inherited Linux capabilities
  - Removed `gosu` package from Dockerfile (no longer needed; `setpriv` is part of the base image)
