# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/), and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [0.5.0] - 2024-02-01

### Added

* Created `libqtip.lua`, a collection of wrapper for the LibQTip-1.0 library.
* Added the sections "Tools Used" and "References" to `README.md`.

### Changed

* Updated `CHANGELOG.md` with recent changes.
* Updated `README.md` by updating the "Disclaimer" section.
* Updated `README.md` with API for `libqtip.lua`.

### Fixed

* Corrected some spelling errors in `README.md`.

## [0.4.0] - 2024-02-01

### Added

* Created `worldmap.lua`, a collection of utilities for the World Map.

### Changed

* Updated `CHANGELOG.md` with recent changes.
* Updated `README.md` with API for `worldmap.lua`.

## [0.3.2] - 2024-01-31

### Added

* Added `:ClearUserWaypoint()` which can remove a previously created waypoint to `handynotes.lua`.

### Changed

* Updated `CHANGELOG.md`.
* Updated `README.md` with changed doc strings.
* Updated documentation strings in `handynotes.lua`.

## [0.3.1] - 2024-01-31

### Changed

* Updated `README.md` with changed doc strings.
* Updated documentation strings in `achievements.lua`.

## [0.3.0] - 2023-11-06

### Added

* Created `handynotes.lua`, a collection of utilities for HandyNotes plugins.

### Changed

* Updated `CHANGELOG.md` with all changes up to this point.
* Updated `README.md` with API for `handynotes.lua`.

## [0.2.3] - 2023-10-26

### Added

* Added `.GetMainCategoryInfoList()` for retrieving the main category names to `achievements.lua`.

### Changed

* Updated `TODO.txt`.
* Updated `README.md` with API additions.

## [0.2.2] - 2023-09-07

### Added

* Created `.gitignore` file and added the `.vscode` directory.

### Changed

* Updated `README.md`.
* Updated `achievements.lua` by renaming `ns.util` to `ns.utils`.

### Removed

* Deleted `.vscode` directory from online repository.

## [0.2.1] - 2023-07-25

### Added

* Added `.GetAchievementLinkWithIcon()` which returns the achievement hyperlink with it's icon prepended to `achievements.lua`.

### Changed

* Updated `README.md`.
* Updated `achievements.lua` by resetting the achievement `name` to `criteriaString`.

## [0.2.0] - 2023-07-04

### Added

* Created `achievements.lua`, a collection of utilities handling achievements.

### Changed

* Updated `README.md` with API for `achievements.lua`.
* Updated `README.md` with info of common usage.

## [0.1.1] - 2023-07-02

### Added

* Created `CHANGELOG.md` and `TODO.txt` files.

### Changed

* Updated `README.md`.

## [0.1.0] - 2023-06-30

### Added

* Initialized project on GitHub (which creates `LICENSE` and `README.md` files).
* Initial commit.

<!-- [Unreleased]: https://github.com/erglo/wow-addon-utilities/compare/v0.4.0...development -->
[0.5.0]: https://github.com/erglo/wow-addon-utilities/compare/v0.4.0...v0.5.0
[0.4.0]: https://github.com/erglo/wow-addon-utilities/compare/v0.3.2...v0.4.0
[0.3.2]: https://github.com/erglo/wow-addon-utilities/compare/v0.3.1...v0.3.2
[0.3.1]: https://github.com/erglo/wow-addon-utilities/compare/v0.3.0...v0.3.1
[0.3.0]: https://github.com/erglo/wow-addon-utilities/compare/v0.2.3...v0.3.0
[0.2.3]: https://github.com/erglo/wow-addon-utilities/compare/v0.2.2...v0.2.3
[0.2.2]: https://github.com/erglo/wow-addon-utilities/compare/v0.2.1...v0.2.2
[0.2.1]: https://github.com/erglo/wow-addon-utilities/compare/v0.2.0...v0.2.1
[0.2.0]: https://github.com/erglo/wow-addon-utilities/compare/v0.1.1...v0.2.0
[0.1.1]: https://github.com/erglo/wow-addon-utilities/compare/v0.1.0...v0.1.1
[0.1.0]: https://github.com/erglo/wow-addon-utilities/releases/tag/v0.1.0
