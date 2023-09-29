# Changelog

## [3.1.0] - 2023/09/29

### Added

- Bazel: Find clang-format on various operating systems

### Changed

- Bazel: Compile build targets in optimized mode by default
- Bazel: Compile coverage and test targets in debug mode by default
- Python: Move all code to a separate [mpacklog.py](https://github.com/tasts-robots/mpacklog.py) project

## [3.0.0] - 2023/06/06

### Added

- (Python: Synchronous ``SyncLogger`` class)

### Changed

- CI: Update Bazelisk script
- (Python: Rename ``Logger`` to ``AsyncLogger``)
- (Python: Remove unused ``mypy_integration``)

## [2.1.0] - 2023/04/26

### Changed

- Make code compatible with macOS (thanks to @boragokbakan)

## [2.0.0] - 2022/09/01

### Added

- (Python: Dump log to CSV from the command line)
- (Python: Dump log to JSON from the command line)
- (Python: Dump log to Python script from the command line)
- (Python: List log fields from the command line)
- (Python: `Logger` implementation)
- (Python: `mpacklog` command-line tool)
- (Python: Unit tests for Python API)

## [1.0.0] - 2022/08/17

First release of the project.
