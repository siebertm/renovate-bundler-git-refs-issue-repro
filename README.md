# Reproduction repo for issue with renovate+bundler+git-tags issue

This repository is a reproduction of an issue with renovate, bundler and git tags.

When renovate finds a git dependency in `Gemfile` and finds an update for it, the tag is applied wrongly.

The relevant part of the `Gemfile` is:

```ruby
gem 'rails', '~> 7.2.1', git: 'https://github.com/rails/rails.git', tag: 'v7.2.1'

```

When running `renovate` using `LOG_LEVEL=debug npx renovate --platform=local`, the update to rails is found, but renovate wants to use the tag `vv7.2.2` instead of `v7.2.2`.

```

```
