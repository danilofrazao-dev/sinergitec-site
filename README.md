# sinergitec.com.br — site source mirror

Local git mirror of the **live** site as served from the production VPS.

- **Live URL:** https://sinergitec.com.br/
- **Production host:** `vps` (root@174.138.41.18, DigitalOcean, Ubuntu 24.04.4 LTS)
- **Production path:** `/var/www/sinergitec/` (owner `www-data:www-data`)
- **Pulled:** 2026-09-13

## Authority

**The VPS copy is the source of truth. This repo is READ-ONLY relative to it.**

Do not edit this repo and treat it as authoritative. Any change here must be
pushed to the VPS deliberately, with a backup taken first (see the existing
`/var/www/sinergitec-bk-*.html.bak` convention on the host).

## Verified baseline (sha256)

Hashes below were taken on the VPS and confirmed byte-for-byte on the local
copy at pull time.

| File | sha256 |
|---|---|
| `index.html` | `b6a9018ba31d7e4b82f5871271183455e333eae84d341621cdcf5f96673c64cf` |
| `Assets/logo.png` | `e009e77e4b9f74d93cab1d8e5733306b7624553f5cb4ad06bd2981c51c09e286` |
| `Assets/logo_full.png` | `e009e77e4b9f74d93cab1d8e5733306b7624553f5cb4ad06bd2981c51c09e286` |
| `Assets/sinergitec_intro.mp4` | `eddf9f868eccd02441961ab4c46fdc3fe8a04388b250ae82640f94b6f538ca76` |

To re-verify:

```bash
ssh vps 'cd /var/www/sinergitec && find . -type f -exec sha256sum {} \; | sort -k2'
certutil -hashfile index.html SHA256   # from this repo root
```

## Layout

```
index.html              main page (sinergitec.com.br)
Assets/                 logo, favicon, intro video, app screenshot, demo video
2dgame/                 sub-project
2dgame-mobile/          sub-project
flip-clock/             sub-project
kaleidoscope/           sub-project (Apple II HGR simulator)
red-led-banner/         sub-project
```

## Brand colours (extracted from Assets/logo.png)

| Color | Hex | RGB | Role |
|---|---|---|---|
| Green | `#33874C` | 51,135,76 | Primary brand green (98.2% of logo green pixels) |
| Blue | `#195E7C` | 25,94,124 | Secondary brand colour |

## Notes

- Live Stripe Payment Link on the main page: `buy.stripe.com/7sYdR25vo8Zxc2l0hifQI04`
  (VoiceLink — R$ 49.90 BRL).
- The VPS keeps dated backups alongside the site: `sinergitec-bk-*.html.bak` and
  `sinergitec_intro-bk-*.mp4`.
