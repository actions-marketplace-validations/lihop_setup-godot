# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased](https://github.com/lihop/setup-godot/compare/v2.0.1...HEAD)

## [2.0.1](https://github.com/lihop/setup-godot/compare/v2.0.0...v2.0.1) - 2022-09-29

### Fixed

- Fixed segmentation fault when running Godot on Windows by pinning mesa-dist-win
  version to 22.1.7. A segmentation fault occurs when running Godot with the most
  recent version (22.2.0).

## [2.0.0](https://github.com/lihop/setup-godot/compare/v1.0.2...v2.0.0) - 2022-08-26

### Changed

- Changed default Godot version to 3.5-stable.

### Security

- Updated node modules using `npm audit fix`.

## [1.0.2](https://github.com/lihop/setup-godot/compare/v1.0.0...v1.0.2) - 2022-08-10

### Fixed

- Fixed "Unable to fetch some archives" error that would sometimes occur after running `apt-get install`
  by running `apt-get update` beforehand.

## [1.0.1](https://github.com/lihop/setup-godot/compare/v1.0.0...v1.0.1) - 2022-07-13

### Fixed

- Fixed "command not found" error for `xset`.

## [1.0.0](https://github.com/lihop/setup-godot/compare/v0.1.1...v1.0.0) - 2022-05-15

### Added

- [#6](https://github.com/lihop/setup-godot/issues/6): Added boolean `export-templates` input. If set to `true` export templates for the specified Godot version will be downloaded and cached in addition to the Godot executable.
- Start X11 server and dummy sound device on Linux runner. This means that executables requiring an X11 server (such as exported projects) will not need to be run with xvfb-run. The server will be started on $DISPLAY. If the DISPLAY environment variable is not set it will default to ':0' and DISPLAY will be set.
- This CHANGELOG file to keep a track of changes between releases.

### Changed

- Default Godot version from 3.4-stable -> 3.4.4-stable.
- Made package managers (i.e. APT, Chocolatey) less noisy.
- [#4](https://github.com/lihop/setup-godot/issues/4): Log a warning and keep going if cache save/restore failed.

### Fixed

- Handling of symlinks when `path` already exists. If `path` exists and is already a symlink to `target`, nothing needs to be done, otherwise `path` will be deleted, replaced with a symlink to `target`, and a warning logged.
- The `choco install mono` command occassionally times out, so retry it a few times.

### Security

- Updated node modules using `npm audit fix`.

## [0.1.1](https://github.com/lihop/setup-godot/compare/v0.1.0...v0.1.1) - 2021-12-17

### Fixed

- Package installation for ubuntu-latest 32-bit.

## [0.1.0](https://github.com/lihop/setup-godot/compare/v0.0.0...v0.1.0) - 2021-11-08

### Added

- [#1](https://github.com/lihop/setup-godot/issues/1): Support for the mono build.
- Caching support. Downloads will now be saved/restored to/from cache if possible. Can be disabled by setting `cache` input to false.

### Changed

- Default version is now 3.4-stable.
- Stable versions >= 3.4 are now downloaded from the godotengine repo [releases](https://github.com/godotengine/godot/releases) rather than tuxfamily.org.

## [0.0.0](https://github.com/lihop/godot-setup/tags/v0.0.0) - 2021-07-24

### Added

- Initial release.
