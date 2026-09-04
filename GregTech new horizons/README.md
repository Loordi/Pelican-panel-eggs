# GregTech: New Horizons Pelican Egg

A Pelican egg for modern-Java GregTech: New Horizons server packs. It supports stable, beta, release-candidate and daily builds.

Use [`Pelican-GTNH-egg.json`](Pelican-GTNH-egg.json) for new installations. The egg is designed to follow future GTNH releases as long as the official download locations, package names and server layout remain compatible.

## Features

- Installs the latest stable release or an exact stable, beta or release-candidate version.
- Installs the latest daily build or a specific daily build number.
- Downloads daily builds from the official GTNH GitHub releases without requiring a GitHub token.
- Includes Java 17, 21, 25 and 26 container images. Select a Java version supported by the chosen GTNH server pack. Java 26 currently requires a daily package labelled Java 17–26.
- Uses 95% of the container memory limit for the Minecraft server.
- Downloads, extracts and validates an update before replacing the active modpack files.
- Automatically confirms the Forge/FML update prompt when the server starts.

## Install and update

Import [`Pelican-GTNH-egg.json`](Pelican-GTNH-egg.json) into Pelican and create a server from it.

For stable, beta and release-candidate builds:

- Set `GTNH_DAILY` to `false`.
- Set `GTVERSION` to `latest` or an exact version such as `2.8.0`, `2.9.0-beta-1` or `2.9.0-rc-1`.

For daily builds:

- Set `GTNH_DAILY` to `true`.
- Set `GTNH_DAILY_BUILD` to `latest` or a build number.
- `GTVERSION` is ignored while daily mode is enabled.

To update an existing server:

1. Stop the server and create a full backup.
2. Select the wanted version and a compatible Java image in the startup menu.
3. Reinstall the server.
4. Wait until the installer reports that installation completed successfully.
5. Refresh the Pelican page and start the server.

The installer cannot start the server automatically after a reinstall. If a server was migrated from an older egg, reset its startup command to the egg default if it still contains `SERVER_MAXRAM`.

## Data preserved during reinstall

World folders are left untouched during reinstall. A full backup is still strongly recommended.

The following paths are backed up and restored automatically:

- `config/JourneyMapServer`
- `server.properties`
- `ops.json`
- `whitelist.json`
- `banned-players.json`
- `banned-ips.json`
- `serverutilities/server/ranks.txt`
- `serverutilities/server/players.txt`

The modpack's `config` directory, except for JourneyMapServer, as well as `libraries`, `mods`, Java argument files and the Forge-patched server file are replaced during reinstall. Back up custom configuration and custom mods separately.

`serverutilities/serverutilities.cfg` is intentionally not preserved so that updated defaults from the modpack can be installed. If you use ServerUtilities ranks, check the ranks section in that file after reinstall and enable it again when necessary.

> **Always back up the complete server, especially the world, before reinstalling.**

## Legacy eggs

Historical and version-specific eggs are stored in [`legacy`](legacy/). They are retained for reference and are not recommended for new installations.

The root-level [`Pelican-GTNH-2.8.X-egg.json`](Pelican-GTNH-2.8.X-egg.json) remains as a compatibility copy for installations using the old update URL. Its update URL points to the new universal filename.

## Compatibility note

“Universal” means that version and Java-package detection are no longer hard-coded to one release series. A future GTNH change to its download service, archive naming or server file layout may still require an egg update.

## Changelog

### 2026-09-04

- Replaced the 2.8.x-specific main egg with the universal egg.
- Added stable, beta, release-candidate and daily build detection.
- Removed the GitHub-token requirement for daily builds.
- Added dynamic Java-range package detection and Java 26 image support.
- Added `server.properties` and `serverutilities/server/players.txt` to reinstall preservation.
- Removed the obsolete `SERVER_MAXRAM` environment variable.
- Moved historical/version-specific eggs to `legacy`.

### Earlier changes

- Added support for daily builds and exact daily build selection.
- Changed server memory allocation to 95% of the Pelican container limit.
- Added beta support and an egg icon.
- Added reinstall preservation for JourneyMapServer, operators, allowlist, bans and ServerUtilities ranks.
- Removed `serverutilities/serverutilities.cfg` from reinstall preservation so modpack updates can replace it.

## More information

- [GTNH Wiki — Server Setup & Update Guide](https://wiki.gtnewhorizons.com/wiki/Server_Setup#Server_Update)
- [GTNH Official Downloads](https://www.gtnewhorizons.com/downloads/)
- [GTNH Discord](https://discord.gg/gtnh)
- [Pterodactyl version](https://github.com/Loordi/Pterodactyl-eggs/tree/main/GregTech%20new%20horizons)
