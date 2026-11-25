# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [0.1.1] - 2026-11-25

### Added

- Add rebase-open-prs workflow (#8)
- replace BUSL-1.1 with proprietary license
- add esbuild bundle step and upload debugAdapter.js as release asset
- add INTERNAL_DEBUG flag and always-on Debug Console output
- auto-create debug DP for manager numbers ≥10
- add struct (user-defined type) support to variable parser
- parse real WinCC OA 3.21 variable protocol format
- centralized test lifecycle + dpConnect retry + fix runnable config
- implement stopOnEntry support for DebugBreak() attach flow
- add DebugBreak/stopOnEntry support via answerOnConnect
- launchRequest spawns WCCOActrl directly; add configurationDoneRequest
- TCP mode via bootstrap.js for pmon auth
- add real WinCC OA integration tests + lifecycle helper
- DatapointClient implementation with tests
- initial setup for winccoa-debug-adapter package

### Fixed

- attach debugAdapter.js as direct asset in pre-release
- deduplicate pre-release trigger and add debugAdapter.js to production release
- correct test assertion — check for InitializedEvent absence, not zero events
- resolve markdownlint MD040/MD060 errors in instructions and docs
- use pathToFileURL for cross-platform ESM dynamic imports
- cross-platform path handling (Windows + Linux support)
- lib BP graying out after reapply + LibId stop event parsing
- resolve library file paths from bt using info libs cache
- library BPs use info libs index after first stop
- use 'info libs' for library breakpoints instead of blind probing
- correct WinCC OA 3.21 command names and add two-phase step response
- serialize setBreakpoints calls to prevent duplicate BPs from race condition
- prevent spurious StoppedEvents from context commands + retry pending breakpoints
- suppress duplicate StoppedEvent during stopOnEntry attach
- use correct WinCC OA GDB-style step command names
- breakpoint stop events now trigger correctly in VS Code
- wire WinCCDebugSession to real WinCC OA 3.21 debugger protocol
- correct WinCC OA 3.21 debugger command protocol
- reduce launch wait 1500ms→300ms, add retry for info scripts
- use scriptId-based breakpoint command (WinCC OA real protocol)
- remove dynamic import of npm-winccoa-core in doLaunch
- pathMappings support empty remote for scripts root
- remove connectionArgs from doAttach — bootstrap.js already connected
- use PmonComponent for project lifecycle, fix config template
- use official winccoa-manager package
- use winccoaconnection.node + dependency injection

### Changed

- deps-dev(deps-dev): bump esbuild from 0.28.0 to 0.28.2 (#67)
- bump actions/setup-node from 6 to 7 (#52)
- bump @winccoa-tools-pack/npm-winccoa-core (#35)
- deps-dev(deps-dev): bump @humanfs/node from 0.16.7 to 0.16.8 (#61)
- deps-dev(deps-dev): bump markdownlint from 0.40.0 to 0.42.2 (#59)
- deps-dev(deps-dev): bump brace-expansion from 1.1.12 to 1.1.22 (#65)
- deps-dev(deps-dev): bump tsx from 4.21.0 to 4.23.15 (#60)
- deps-dev(deps-dev): bump typescript-eslint from 8.59.1 to 8.73.0 (#62)
- bump smol-toml and markdownlint-cli (#64)
- deps-dev(deps-dev): bump linkify-it from 5.0.0 to 5.0.2 (#53)
- align .github with template-npm-shared-library (#58)
- deps-dev(deps-dev): bump @types/node (#3)
- deps-dev(deps-dev): bump prettier (#10)
- bump softprops/action-gh-release from 2 to 3 (#13)
- bump picomatch from 4.0.3 to 4.0.4 (#21)
- deps-dev(deps-dev): bump flatted from 3.3.3 to 3.4.2 (#22)
- deps-dev(deps-dev): bump typescript-eslint from 8.56.1 to 8.59.1 (#26)
- bump actions/github-script from 8 to 9 (#14)
- bump actions/upload-artifact from 6 to 7 (#2)
- deps-dev(deps-dev): bump globals from 17.4.0 to 17.6.0 (#11)
- bump docker/setup-buildx-action from 3 to 4 (#1)
- switch license from MIT to BSL-1.1 (2 user limit, Apache 2.0 after 2028-04-12)
- update instructions.md — current test status + open findings
- update instructions with WinCC OA 3.21 protocol details and known issues
- add instructions.md with architecture, known issues and next steps
- wip: pending BP retry timer + progs all-manual + lifecycle fixes
- add adapter-level regression tests for race condition and lib BP
- wip: lib:N breakpoint probing + 3-click fix (call_library_function.ctl line 14)
- comprehensive step/pause/print integration tests + fix cli --help stdout
- replace debugger-poc with runnable fixture project
- add E2E fixture and full breakpoint cycle integration test
- add unit tests for WinCC OA 3.21 protocol quirks
- wip: fix manager startup and DPE paths in DatapointClient

## [0.2.0] - 2026-03-03

### Changed

- Add changelog generation and validation scripts, update workflows, and repository settings (#33)
- Add peer dependencies to package-lock.json and implement CLI tests for argument parsing (#32)
- update template
- Add actions to sync org and template files
- Update sync-template-files.yml
- Update sync-template-files.yml
- Create sync-template-files.yml
- Create sync-org-files.yml
- Update bug_report.yml
- upmerge from core npm
- bump actions/upload-artifact from 5 to 6
- add setup-gitflow and gitflow-action workflows
- Add Buy Me a Coffee funding option

## [Unreleased]

### Documentation

- Align README CLI/API examples with actual tool behavior (in-place conversion, required version).

## [0.1.0] - 2026-02-28

### Added

- Core converter `PnlXmlConverter` wrapping WinCC OA `WCCOAui` `-xmlConvert`.
- CLI `winccoa-pnl-xml` with `convert pnl-to-xml` / `convert xml-to-pnl`.
- TypeScript API convenience functions `pnlToXml()` and `xmlToPnl()`.
- Unit tests covering CLI parsing, API wrappers, and converter arguments.
