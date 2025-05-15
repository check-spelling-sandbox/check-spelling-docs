# Automatically remove persisted-credentials

Most of the time when check-spelling is run with `checkout: true`, it has no use for credentials after the checkout step finishes.

Users would like the security of not having credentials lying around, and this seems like a reasonable feature. 

## Background

It's an optional feature of [actions/checkout](https://github.com/actions/checkout) in the form of the [`persist-credentials`](https://github.com/actions/checkout/blob/85e6279cec87321a52edac9c87bce653a07cf6c2/action.yml#L52-L53) flag.

Unfortunately, [actions/checkout](https://github.com/actions/checkout)'s implementation interacts poorly with `git`'s submodules feature, and it [doesn't work for repositories with submodules in some circumstances](https://github.com/actions/checkout/issues/1358).

Generally, check-spelling with `checkout: true` doesn't check submodules anyway.

## Approach 

check-spelling as of [v0.0.25](http://github.com/check-spelling/check-spelling/releases/tag/v0.0.25) when set to `checkout: true` will remove persisted unless it is [updating the expect list](./Feature:-Update-expect-list.md).

It does not use the `actions/checkout` implementation, although the general behavior is the same:
1. `actions/checkout` sets up a repository (with the credentials necessary to fetch)
2. `actions/checkout` fetches the repository data (using the configured credentials)
3. `actions/checkout` checks out the desired reference
4. _something_ attempts to iterate over the checked out repository to remove the credentials

The implementation lives in [`remove-persisted-credentials`](https://raw.githubusercontent.com/check-spelling/check-spelling/eca22f4/wrappers/remove-persisted-credentials).

---
[FAQ](FAQ.md) | [Showcase](Showcase.md) | [Event descriptions](Event-descriptions.md) | [Configuration information](Configuration-information.md) | [Known Issues](Known-Issues.md) | [Possible features](Possible-features.md) | [Deprecations](Deprecations.md) | [Release notes](Release-notes.md) | [Helpful scripts](Helpful-scripts.md)
