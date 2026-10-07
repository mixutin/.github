# Garry's Mod Ultimate — Pterodactyl Egg

A feature-rich PTDL_v2 egg for hosting Garry's Mod on Pterodactyl.

## Highlights

- SteamCMD installation with Garry's Mod Dedicated Server App ID `4020`
- Stable (`public`), `x86-64`, `dev`, and `prerelease` Steam branches
- Selectable `srcds_run` / `srcds_run_x64`
- Branch-aware automatic updates on every start
- Optional SteamCMD file validation
- Steam Workshop collection mounting
- Workshop auto-update toggle
- `cfg/srcds_workshop_ids.txt` created for the newer individual Workshop-ID workflow
- Steam Game Login Token (GSLT)
- Map, gamemode, slots, tickrate
- Server name and join password
- RCON password
- Server-browser location, hide-server, and LAN-only controls
- FastDL and loading-screen URLs
- Lua refresh control
- Garry's Mod P2P mode
- Extra startup arguments without shell `eval`
- Graceful `quit` shutdown command
- Panel-managed config written to `garrysmod/cfg/pterodactyl.cfg`
- Your own `garrysmod/cfg/server.cfg` is kept separate and is not overwritten on restart
- Uses the maintained `ghcr.io/ptero-eggs/steamcmd:debian` runtime image

## Import

Download `egg-garrys-mod-ultimate.json`.

In Pterodactyl:

1. Open **Admin → Eggs**.
2. Click **Import Egg**.
3. Upload `egg-garrys-mod-ultimate.json`.
4. Create a server using **Garry's Mod Ultimate**.
5. Allocate the normal game port (commonly 27015, or whatever allocation your panel gives the server).

The egg uses the server's primary Pterodactyl allocation automatically.

## Recommended profiles

### Stable 32-bit

- Steam Branch: `public`
- Server Binary: `srcds_run`
- Auto Update: `1`

### x86-64

- Steam Branch: `x86-64`
- Server Binary: `srcds_run_x64`
- Auto Update: `1`

If `srcds_run_x64` is requested but unavailable, the startup wrapper logs a warning and falls back to `srcds_run`.

### Development / prerelease

Set Steam Branch to `dev` or `prerelease`. These can be less stable than the public branch.

## Workshop

For a collection, put its numeric ID in **Workshop Collection ID**. Garry's Mod will download and mount the collection on startup.

The collection must be public or unlisted.

This egg also creates:

`garrysmod/cfg/srcds_workshop_ids.txt`

That file can be edited if you want to manage individual Workshop addon IDs instead of, or in addition to, a collection.

Set **Workshop Auto Update** to `0` if you intentionally want Workshop content pinned between restarts. That can reduce surprise addon changes, but mismatched map/addon versions can stop clients from joining.

## GSLT

Set **Steam Game Login Token** to your Steam Game Server Login Token. Facepunch recommends a GSLT for normal public dedicated-server operation.

## Configuration layout

Panel-controlled values are regenerated on every start in:

`garrysmod/cfg/pterodactyl.cfg`

Put persistent custom convars, sandbox limits, addon configuration, networking tweaks, etc. in:

`garrysmod/cfg/server.cfg`

The installer creates a conservative starter `server.cfg` only when one does not already exist.

## Auto update and validation

The runtime image's generic SteamCMD auto-update is intentionally disabled through a hidden `AUTO_UPDATE=0` variable.

Instead, the egg's own wrapper uses **GMOD_AUTO_UPDATE**. This lets the update command include the selected Steam beta branch, which matters when moving between `public`, `x86-64`, `dev`, and `prerelease`.

Enable **Validate Files On Update** only when you need the extra integrity check or are repairing an install; it makes update checks slower.

## Custom startup arguments

**Custom Startup Arguments** accepts simple space-separated SRCDS arguments and appends them as an argument array without shell `eval`.

Example:

`-nohltv +con_logfile console.log`

For settings containing complex strings or spaces, prefer `server.cfg`.

## Files

- `egg-garrys-mod-ultimate.json` — importable Pterodactyl egg
- `scripts/install.sh` — standalone copy of the installation script embedded in the egg
- `scripts/start.sh` — runtime wrapper embedded by the installer
- `examples/server.cfg` — optional starter configuration
- `CHANGELOG.md` — release history

## References

- Pterodactyl custom egg documentation: https://docs.pterodactyl.io/v2/guides/egg-creation/creating-custom-egg
- Garry's Mod dedicated server guide: https://wiki.facepunch.com/gmod/Downloading_a_Dedicated_Server
- Garry's Mod Linux server guide: https://wiki.facepunch.com/gmod/Linux_Dedicated_Server_Hosting
- Garry's Mod Workshop server guide: https://wiki.facepunch.com/gmod/Workshop_for_Dedicated_Servers

## License

The custom egg files in this directory are provided under the MIT License.
