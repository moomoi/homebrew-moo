# homebrew-moo

Homebrew tap for [Moo](https://moo.moi), the keyboard launcher for macOS.

```sh
brew install --cask moomoi/moo/moo
```

Installs `Moo.app` into `/Applications` and links the `moo` command line client onto your PATH
(`moo search …`, `moo ask …`, `moo --help`). Universal: Apple silicon and Intel, macOS 14 or later.

## Upgrade and uninstall

```sh
brew update && brew upgrade --cask moo
brew uninstall --cask moo          # add --zap to remove Moo's settings, history and caches
brew untap moomoi/moo
```

`--zap` also removes `~/Library/Application Support/Moo`, `~/Library/Caches/Moo` and
`~/Library/Preferences/moi.moo.launcher.plist`. Keys Moo saved in the Keychain stay; remove them
in Keychain Access (search "Moo").

## How the cask is updated

Each public Moo release on [moomoi/moo](https://github.com/moomoi/moo/releases) sends a `release`
event here. **Update formulas** (`.github/workflows/update-formulas.yml`) downloads
`Moo-macos-universal.dmg`, computes its SHA-256 and rewrites `Casks/moo.rb`. To run it by hand,
dispatch **Update formulas** with the version.
