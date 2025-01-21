# #33005 Reproduction repo for issue with renovate+bundler+git-tags issue

This repository is a reproduction of an issue with renovate, bundler and git tags. (see https://github.com/renovatebot/renovate/discussions/33005)

# Current behavior

When renovate finds a git dependency in `Gemfile` and finds an update for it, the tag is applied wrongly.

The relevant part of the `Gemfile` is:

```ruby
gem 'rails', '~> 7.2.1', git: 'https://github.com/rails/rails.git', tag: 'v7.2.1'
```

When running `renovate` using `LOG_LEVEL=debug npx renovate --platform=local`, the update to rails is found, but renovate wants to use the tag `vv7.2.2` instead of `v7.2.2`. (note the doubled `v`)

# Expected behavior
The tag used should not duplicate the `v`. In the specific example, I expect renovate to upgrade to `v7.2.2`

# Link to the Renovate issue or Discussion
[Link to discussion](https://github.com/renovatebot/renovate/discussions/33005)
