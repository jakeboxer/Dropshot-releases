# Dropshot public site

A static rave-inspired download site for Dropshot. This public repository can also host downloadable DMGs as GitHub Release assets. The app source lives separately.

## Local preview

From this directory, run:

```sh
python3 -m http.server 8000 --bind 127.0.0.1
```

Open <http://127.0.0.1:8000>. Stop the server with Ctrl-C. There are no dependencies or build step; page markup is in `index.html` and styles are in `style.css`. Anton is self-hosted in `assets/` with its SIL Open Font License.

## Publishing

The publishing source is **main**, **/(root)**, configured in [repository Pages settings](https://github.com/jakecard/Dropshot-releases/settings/pages). `.nojekyll` tells Pages to serve the static files without Jekyll processing.

Commit changes and push to `main` to publish. Check the Pages deployment in [Actions](https://github.com/jakecard/Dropshot-releases/actions), then verify the project URL at <https://jakecard.dev/Dropshot-releases/>.

The site inherits the `jakecard.dev` custom domain from `jakecard/jakecard.github.io`, with HTTPS enforced. Keep `https://jakecard.dev/Dropshot-releases/appcast.xml` reachable: installed apps use this stable URL for automatic update checks.

See [GitHub's publishing-source documentation](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site).

## Downloads and updates

Both download links point to the latest `Dropshot.dmg` asset in `jakecard/Dropshot-releases`. Upload each signed DMG to its immutable release tag before publishing its entry in `appcast.xml`. Feed enclosure URLs must use the tag-specific asset URL, not `releases/latest/download`.

Preserve the app bundle identifier, Sparkle public key, and existing feed URL when changing hosting ownership. Verify the website, feed, and downloaded DMG after deployment; a complete update test additionally requires an installed lower-build release and a newer published release.

The page respects reduced-motion preferences and serves `assets/app-icon.webp`.
