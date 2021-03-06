# Changelog
All notable changes to **Open Coaster Interface** will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]
*No entries* 

## [1.2.0] - 2020-04-10
### Added
- Added new `zone` field for attraction
- Added new `zones` field for attraction

### Fix
- Fixed not working `founded` filter for attractions

### Removed
- Removed attribtute `section` / replaced by `zone` and `zones` field

## [1.1.0] - 2019-11-29
### Added
- \#1 Added new `label` field for history items (park and attraction).
- \#2 Added new `timezone` field for parks (sub field: `key`, `value`, `offset`)
- \#5 Add sorting by GEO location if location filter is active
- Add GEO location fields for attractions
- Add first mutation for adding waiting times
- Add query param `debug` for execute GraphQL requests with logging (for debugging) 

## [1.0.0] - 2019-11-25
### Added
- Initial release
