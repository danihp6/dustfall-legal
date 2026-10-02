# dustfall-legal

Legal pages for Dustfall (`com.dustfall.game`), hosted via GitHub Pages, plus the
`app-ads.txt` AdMob verifies against the account's publisher.

- Privacy Policy (English): https://danihp6.github.io/dustfall-legal/
- Política de Privacidad (Spanish): https://danihp6.github.io/dustfall-legal/privacidad.html
- Developer site: https://dustfall.herreteam.com/
- app-ads.txt: https://dustfall.herreteam.com/app-ads.txt

This is the URL entered in Google Play Console → App content → Privacy policy.

## app-ads.txt

AdMob requires `app-ads.txt` at the **root of the domain** of the developer website
listed in the store listing, so the site is served from the custom domain
`dustfall.herreteam.com` (the `CNAME` file). Without the custom domain the file would
only be reachable at `danihp6.github.io/dustfall-legal/app-ads.txt`, which AdMob does
not check.

Order matters, because GitHub Pages redirects `danihp6.github.io/dustfall-legal/` to
the custom domain as soon as the `CNAME` file lands:

1. Add the Cloudflare DNS record `dustfall` (CNAME → `danihp6.github.io`), proxied or
   DNS-only. DNS-only lets GitHub Pages provision its own Let's Encrypt certificate.
2. Push the `CNAME` file (this repo) so Pages serves `dustfall.herreteam.com`.
3. In Play Console → Store settings → **Developer website**, set
   `https://dustfall.herreteam.com/`.
