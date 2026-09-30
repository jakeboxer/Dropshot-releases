# Dropshot public site

A static rave-inspired download site for Dropshot. This public repository can also host downloadable DMGs as GitHub Release assets. The app source lives separately.

## Local preview

From this directory, run:

```sh
python3 -m http.server 8000 --bind 127.0.0.1
```

Open <http://127.0.0.1:8000>. Stop the server with Ctrl-C. There are no dependencies or build step; page markup is in `index.html` and styles are in `style.css`. Anton is self-hosted in `assets/` with its SIL Open Font License.

## Publishing

The publishing source is **main**, **/(root)**, configured in [repository Pages settings](https://github.com/jakeboxer/Dropshot-releases/settings/pages). `.nojekyll` tells Pages to serve the static files without Jekyll processing.

Commit changes and push to `main` to publish. Check the Pages deployment in [Actions](https://github.com/jakeboxer/Dropshot-releases/actions), then verify the project URL at <https://jakeboxer.github.io/Dropshot-releases/>.

The site uses the default GitHub Pages domain with HTTPS enforced. No custom domain is configured.

See [GitHub's publishing-source documentation](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site).

## Scope

The download control explicitly says “coming soon” until a public installer exists. When a release is published, replace the disabled button with an anchor to the verified release asset, update the availability copy, and verify the listed macOS and architecture requirements.

The page respects reduced-motion preferences. The user-provided raw app icon is included unchanged in `assets/app-icon.png`; the earlier screenshot remains reference-only. Custom domains and an update feed are outside this design change.
