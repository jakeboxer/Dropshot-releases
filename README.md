# Dropshot releases

This repository hosts Dropshot's GitHub Release downloads (DMGs). The app source lives separately. GitHub Pages is disabled here.

The website, Sparkle update feed, and old website redirect are maintained directly in [jakecard/jakecard.github.io](https://github.com/jakecard/jakecard.github.io):

- Website: <https://jakecard.dev/dropshot/>
- Update feed: <https://jakecard.dev/dropshot/appcast.xml>

## Publishing releases

Upload each signed DMG to its immutable release tag here before publishing its feed entry in `jakecard.github.io/dropshot/appcast.xml`. Enclosure URLs must remain tag-specific, such as `https://github.com/jakecard/Dropshot-releases/releases/download/build-18/Dropshot.dmg`, not `releases/latest/download`.

In the `jakecard.github.io` checkout, commit and publish the updated `dropshot/appcast.xml`. See that repository's README for the complete publishing procedure.

Preserve the app bundle identifier and Sparkle public key. Verify the feed and the downloaded DMG after deployment; a complete update test additionally requires an installed lower-build release and a newer published release.
