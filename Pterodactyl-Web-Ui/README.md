# NOVA Web Player — deployment guide

## Directory structure — WHERE THIS GOES ON THE SERVER

This mirrors the Pterodactyl Nginx Egg's expected layout exactly:

```
/home/container/                  <- server root (egg's home)
├── config.php                    <- ⚠️ EDIT THE PASSWORD IN THIS FILE FIRST
├── data/                         <- created automatically on first run (SQLite lives here)
└── www/                          <- egg's public web root — everything below goes here
    ├── web.html                  <- open this in a browser
    ├── api/
    │   ├── login.php, logout.php, me.php
    │   ├── users.php             (admin: list/add/delete users)
    │   ├── settings.php          (per-user: NextCloud/Subsonic source config)
    │   ├── playlists.php         (per-user: playlist CRUD)
    │   ├── library.php           (lists tracks from the user's configured source)
    │   └── stream.php            (proxies raw .nova bytes, with Range support)
    └── includes/
        ├── db.php, auth.php, nextcloud.php, subsonic.php
```

**Before deploying**: open `config.php` and change `DEFAULT_ADMIN_PASS` from the
placeholder. This value is only read ONCE, the very first time the app runs (when the
database doesn't exist yet) — after that, the real admin account lives in the database,
so changing your password via the admin panel later works correctly and isn't
overridden by this file.

## Why the database lives outside `www/`

`data/app.db` (created automatically) sits one level above the web root on purpose —
verified during testing that this path structurally cannot be reached by any HTTP
request nginx would serve, regardless of nginx config changes. This matters because the
egg's auto-update system explicitly overwrites nginx configs on update — so a security
boundary that depended on an nginx rule I added would be fragile. This one isn't.

## Access paths

- **Local/LAN**: `nginx-configs/home-music-cosmoscraft-net.conf` — proxies
  `music.cosmoscraft.net` to `10.0.0.152:2030` for clients on the home network
  (assumes Technitium resolves the domain locally for LAN clients).
- **Public/internet**: `nginx-configs/CLOUDFLARE_TUNNEL_SETUP.md` — walks through the
  egg's own built-in Cloudflare Tunnel (cloudflared), which connects directly from the
  container to Cloudflare's edge. No separate reverse proxy needed for this path.

## What's genuinely tested vs. what isn't

**Tested with real HTTP requests** (PHP's built-in server + curl): login/logout,
session persistence, wrong-password rejection, admin user CRUD (including duplicate
username rejection, self-delete protection, last-admin protection), settings
save/upsert, playlist CRUD, unauthenticated access correctly blocked, NextCloud PROPFIND
XML parsing against a realistic multi-folder response (caught and fixed a real PHP
`SimpleXMLElement` boolean-conversion bug in the process), and an unreachable-source
error path.

**Not tested** (couldn't be, from this environment): an actual NextCloud server, an
actual Subsonic-compatible server, the browser-side JS (login form, library rendering,
playback, admin panel UI) — these need a real browser and real upstream servers, which
is the first real test once this is deployed.

## Known limitations, stated plainly

- **Subsonic support is experimental.** Stock Subsonic-compatible servers (Navidrome,
  etc.) index media by recognized file extension — `.nova` is not one they know, so
  this will likely return an empty library unless your specific server has been
  configured to expose unrecognized file types. NextCloud is the reliable path.
- **Library metadata is read via partial HTTP Range fetches** (first ~600KB per track)
  rather than full downloads, to keep library browsing fast. Very large embedded
  artwork could occasionally get truncated as a result — audio playback itself is
  unaffected either way, since that always fetches the complete file.
- **The `FRP_LOCAL_PORT` / Linode nginx config was removed** per your clarification
  that this deployment doesn't go through frp — Cloudflare Tunnel handles the public
  path directly instead.
