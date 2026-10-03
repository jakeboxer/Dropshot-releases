# Dropshot releases

This repository hosts Dropshot's GitHub Release downloads (DMGs). The app source lives separately. GitHub Pages is disabled here.

The website, Sparkle update feeds, and old website redirect are maintained directly in [jakecard/jakecard.github.io](https://github.com/jakecard/jakecard.github.io):

- Website: <https://jakecard.dev/dropshot/>
- Canonical feed: <https://jakecard.dev/dropshot/appcast.xml>
- Compatibility feed for installed apps: <https://jakecard.dev/Dropshot-releases/appcast.xml>

## Publishing releases

Upload each signed DMG to its immutable release tag here before publishing its feed entry in `jakecard.github.io/dropshot/appcast.xml`. Enclosure URLs must remain tag-specific, such as `https://github.com/jakecard/Dropshot-releases/releases/download/build-18/Dropshot.dmg`, not `releases/latest/download`.

In the `jakecard.github.io` checkout, run `python3 scripts/sync-dropshot-feed.py`, then commit and publish both feed files together. The old feed path must continue receiving every update for existing installations. See that repository's README for the complete publishing procedure.

Preserve the app bundle identifier and Sparkle public key. Verify both feeds and the downloaded DMG after deployment; a complete update test additionally requires an installed lower-build release and a newer published release.
