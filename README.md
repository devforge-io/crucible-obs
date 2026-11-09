# Crucible OBS plugin

The OBS Studio plugin for [Crucible](https://github.com/devforge-io/crucible), a self-hosted multistream relay. From inside OBS it pairs with your Crucible server, manages your Twitch, YouTube, Kick and Rumble destinations, points OBS's stream at Crucible, and shows each destination's state in a dock.

This repository hosts the plugin's releases. Downloads are on the [Releases](https://github.com/devforge-io/crucible-obs/releases) page.

## Requirements

- OBS Studio 32 on macOS 12 or later (Apple Silicon or Intel). A Windows build is planned.
- A Crucible server: see [devforge-io/crucible](https://github.com/devforge-io/crucible).

## Install

1. Quit OBS.
2. Download `crucible-obs-<version>-macos-universal.zip` from the latest release and unzip it.
3. Move `crucible-obs.plugin` into `~/Library/Application Support/obs-studio/plugins/`.
4. Start OBS. Setup is under **Tools → Crucible**, status under **Docks → Crucible**.

If a release says it isn't signed and OBS doesn't load it, run:

```sh
xattr -dr com.apple.quarantine ~/Library/Application\ Support/obs-studio/plugins/crucible-obs.plugin
```

## Set up

1. **Server tab:** enter your server's address, such as `https://relay.example.com:8740`. On the server, run `sudo crucible pair`, enter the code it prints, and click **Pair**.
2. **Destinations tab:** add each platform with the server URL and stream key from its dashboard, and tick **On** for the ones to stream to. Keys go to your server once, are stored encrypted there, and are never shown again.
3. **Streaming tab:** click **Use Crucible for streaming**. OBS's Settings → Stream now points at your server. **Restore previous stream settings** puts your old settings back.
4. Click **Start Streaming** in OBS as usual.

## Uninstall

Quit OBS and delete `crucible-obs.plugin` from the plugins folder.

## Licence

GPL-2.0-or-later.
