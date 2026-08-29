# Anyray Homebrew tap

Install the `anyray-connect` CLI on macOS through Homebrew instead of piping an
installer into a shell:

```sh
brew tap anyrayHQ/tap
brew trust anyrayhq/tap          # one-time: Homebrew gates third-party cask taps
brew install --cask anyray-connect
```

The cask installs the Developer ID–signed, notarized `anyray-connect.pkg`
published on each [install release](https://github.com/anyrayHQ/install/releases).
Homebrew verifies the download against the pinned SHA-256 before installing.

`anyray-connect` keeps itself current after install, so the cask declares
`auto_updates true`; Homebrew only bootstraps the trusted install.

## Updating the cask on a new release

The cask is regenerated from the release's `SHA256SUMS` by
`scripts/gen-homebrew-cask.sh` in `anyrayHQ/install`. Copy the rendered
`Casks/anyray-connect.rb` here (or open a `brew bump-cask-pr`) so the pinned
version and hash match the latest release.
