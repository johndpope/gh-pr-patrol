# gh-pr-patrol

This tool keeps PR status-check results up-to-date.
First it searches for **succeeded but outdated** pull-request status checks, then trigger rebuild for each unless the pull-request has `WIP` label.
This way false-positives can be detected before merge, while ignoring positive-falses.

By default outdated means that it passed one day since the last build. Interval can be changed by passing `-i` option.

Currently supports only Bitrise. For other CI services, PRs are welcomed!

# Requirements
- macOS Sierra or later

# Required environment variables

- `GITHUB_REPOSITORY` ... e.g. `toshi0383/Bitrise-iOS`
- `GITHUB_API_TOKEN`
- `BITRISE_API_TOKEN`
- `BITRISE_BUILD_TRIGGER_TOKEN`
- `APP_SLUG`

# Options

- `-i interval` ... Current time minus interval is the threshold to determine if it's "outdated".

# How to use
`export` environment variables above and execute.

Otherwise you can always use this syntax to do that in one-line.

```
GITHUB_REPOSITORY=toshi0383/Bitrise-iOS GITHUB_API_TOKEN= ... gh-pr-patrol
```

# Install
Binary install is recommended for CI usage, but you can build from source.

- SwiftPM
- Mint

# Development

- Swift4+
- Xcode9.3+

# License
MIT
