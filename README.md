# Agents On for Homebrew

[Agents On](https://github.com/brandon-cor/agents-on) keeps your Mac awake with a
green menu bar light, one-click toggling, and optional timers. Requires **macOS 14
or newer** and [Homebrew](https://brew.sh).

Install and start the menu bar app with one paste:

```sh
brew install brandon-cor/tap/agents-on && agents-on install
```

Setup asks once for your Mac password to authorize the two specific sleep
toggles. It installs the app in `~/Applications`, starts it automatically when
you sign in, and verifies that its menu bar indicator responds. Your existing
sleep setting is preserved.

Left-click the light to toggle `agents on` / `agents off`. Right-click for the
30-minute, 1-hour, 3-hour, or custom timer and other settings.

Check the download without setting up the app:

```sh
agents-on verify
```

After setup, these commands are also available:

```sh
agents-on show
agents-on status
agents-on on
agents-on off
agents-on doctor
```

To update both the Homebrew package and your app:

```sh
brew update
brew upgrade brandon-cor/tap/agents-on
agents-on install
```

To remove the app and restore normal sleep, then remove the Homebrew package:

```sh
agents-on uninstall
brew uninstall brandon-cor/tap/agents-on
```

Uninstalling only the Homebrew formula leaves your app and account setup in
place. This formula packages the verified **macOS 0.5.0** release; Windows release
numbers are independent. Both the release archive and the installer are pinned
with SHA-256 checksums.

For contributors, run:

```sh
brew style Formula/agents-on.rb check-stage.rb
brew audit --strict brandon-cor/tap/agents-on
brew ruby check-stage.rb
```

The staging check uses Homebrew's real download and installation logic with a
temporary prefix. It verifies the release and tests command forwarding without
running the account setup or changing sleep settings.
