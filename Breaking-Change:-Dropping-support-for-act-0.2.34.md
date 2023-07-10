# Breaking Change: Dropping support for act 0.2.34

## Background

In theory, `github.action_path` and `env.GITHUB_ACTION_PATH` should be more or less interchangeable and work in all GitHub Action Runtime environments.

Great theory. 🦄  🦷🧚‍♂️ 🎅...

### There were bugs in [nektos/act](https://github.com/nektos/act)

Bug | Fixed in
-|-
[nektos/act#603](https://github.com/nektos/act/issues/603) | [v0.2.22](https://github.com/nektos/act/releases/tag/v0.2.22)
[nektos/act#607](https://github.com/nektos/act/issues/607) | [v0.2.22](https://github.com/nektos/act/releases/tag/v0.2.22)
[nektos/act#1488](https://github.com/nektos/act/issues/1488) | [v0.2.35](https://github.com/nektos/act/releases/tag/v0.2.35)

check-spelling had workarounds for them that relied on `github.action_path` as it was more reliable

### GitHub's [action runner](https://github.com/actions/runner) has bugs

* [actions/runner#716](https://github.com/actions/runner/issues/716) - currently impacts self-hosted runners

## Solution

As the current version of [nektos/act](https://github.com/nektos/act) is [v0.2.46](https://github.com/nektos/act/releases/tag/v0.2.46), it seems like now is a fairly reasonable time to drop support for the workaround and switch to a form that works around the GitHub self-hosted runner bug instead...
