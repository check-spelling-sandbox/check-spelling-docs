# Release notes

## Supported
* [prerelease](#prerelease)
* [v0.0.21](#v0021)

## Unsupported

❗ Please do not use these versions.

* [v0.0.20](#v0020)
* [v0.0.19](#v0019)
* [v0.0.18](#v0018)
* [v0.0.17](#v0017)
* [v0.0.16](#v0016)

## Prerelease

* 🏃 Performance fix for workflows that don't use patterns / forbidden / candidates
* 🔧 Matrixes generate archives that the latest apply.pl can consume (fixes regression in [v0.0.21](https://github.com/check-spelling/check-spelling/releases/tag/v0.0.21))
* 🔧 Matrixes generate sarif reports with distinct categories enabling them all to render properly (fixes bug in [v0.0.21](https://github.com/check-spelling/check-spelling/releases/tag/v0.0.21))

<!--
🛠️ In various states of `prerelease`
🌟 Almost ready to transition from `prerelease` to release 🍽️

-->
## v0.0.21

[v0.0.21](https://github.com/check-spelling/check-spelling/releases/tag/v0.0.21)

* [[Breaking change: Smaller cspell dictionaries]]
* [[Behavior change: File line column notation]]
* [[Step Summary|Feature: Step Summary]]
* [[Sarif output|Feature: Sarif output]]
* [[Suggest patterns|Feature: Suggest patterns]]
* [[Update expect command-line|Feature: Update expect command-line]]
* [[Check commit messages|Feature: Check commit messages]]
* [[Restricted Permissions|Feature: Restricted Permissions]]
* [[Minified file detection|Feature: Minified file detection]]
* [Check filenames and paths `check-file-path`](https://github.com/check-spelling/check-spelling/wiki/Feature%3A-Check-filenames-and-paths#improvements-in-v0021)
* [[Detect binary files|Feature: Detect binary files]]
* [[Disable word collating|Feature: Disable word collating]]
* [[Scan noisy files|Feature: Scan noisy files]]
* [[Workaround broken dependencies|Feature: Workaround broken dependencies]]

## v0.0.20

[v0.0.20](https://github.com/check-spelling/check-spelling/releases/tag/v0.0.20)

* [[Behavior change: Patterns masking character|Behavior change: Patterns masking character]]
* [[Behavior change: Consumed line endings]]
* [[Smarter scheduling 2021 October|Feature: Smarter scheduling 2021 October]]
* [[Suppress push comment for open PRs|Feature: Suppress push comment for open PRs]]
* [[Treat specific errors as warnings|Feature: Treat specific errors as warnings]]
* [[Run locally|Feature: Run locally]] using `act` (note: support for `act` is a bit of a moving target, but in general it should work)
* [[Area dictionaries|Feature: Area dictionaries]]
* [[Suggest Area dictionaries|Feature: Suggest Area Dictionaries]]
* [[Suppress comments|Feature: Suppress comments]]
* [[Matrix support|Feature: Matrix support]]
* [[Only changes|Feature: Only-changes]]
* [[Collapse older check comments|Feature: Collapse older check comments]]
* [[Restricted Permissions|Feature: Restricted Permissions]]
* [[Bug fix: Case changes should fail]]
* [Play nice with `@dependabot`](https://github.com/check-spelling/check-spelling/wiki/@dependabot)
* [[Check filenames and paths|Feature: check filenames and paths]]
* [[Automatically truncate comment|Feature: Automatically truncate comment]]
* [[Perl module testing|Feature: Perl module testing]]
* [[Suggest commit after expect update|Feature: Suggest commit after expect update]]
* [[Forbidden patterns|Feature: Forbidden patterns]]
* [[Configurable file size limits|Feature: Configurable file size limits]]
* [[Duplicate word detection|Feature: Duplicate word detection]]
* [[Update with deploy key|Feature: Update with deploy key]]
* [[Artifacts are zipped|Breaking change: Artifacts are zipped]]
* [[User visible warning codes|Feature: User visible warning codes]]

## v0.0.19

[v0.0.19](https://github.com/check-spelling/check-spelling/releases/tag/v0.0.19)

Information is available in [GHSA-g86g-chm8-7r2p](https://github.com/check-spelling/check-spelling/security/advisories/GHSA-g86g-chm8-7r2p)

## v0.0.18

[v0.0.18](https://github.com/check-spelling/check-spelling/releases/tag/v0.0.18)

* [[Behavior change: Dropping word stemming]]
* [[Behavior change: Ignoring two letter words]]
* [[Update expect list|Feature: Update expect list]]
* [[Collapse older check comments|Feature: Collapse older check comments]]
* [[Suggest adding files to exclude|Feature: Heuristic exclude suggestions]]
* [[First run advice|Feature: First run advice]]
* All unrecognized words are reported in the log, instead of just the ones introduced by the current changes.

## v0.0.17

[0.0.17-alpha](https://github.com/check-spelling/check-spelling/releases/tag/0.0.17-alpha)

* [[Feature: Easier bootstrapping]]
* [[Feature: Spelling comments without config]]
* [[Feature: Run locally]]
* [[Feature: Versioned dictionaries]]
* [[Feature: Support pull_request_target]]

### Known issues

If you're using a private repository, the `push` event won't work correctly.

## v0.0.16

[0.0.16-alpha](https://github.com/check-spelling/check-spelling/releases/tag/0.0.16-alpha)

* [[Feature: Allow]]
* [[Feature: Expectlist]]
* [[Feature: Dictionary deltas]]
* [[Feature: Other shells]]
