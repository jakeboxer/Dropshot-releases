# Dropshot public site

A minimal static website for Dropshot. This public repository can also host downloadable DMGs as GitHub Release assets. The app source lives separately.

## Local preview

From this directory, run:

```sh
python3 -m http.server 8000 --bind 127.0.0.1
```

Open <http://127.0.0.1:8000>. Stop the server with Ctrl-C. There are no dependencies or build step; all page styles are in `index.html`.

## Publishing

The publishing source is **main**, **/(root)**, configured in [repository Pages settings](https://github.com/jakeboxer/Dropshot-releases/settings/pages). `.nojekyll` tells Pages to serve the static files without Jekyll processing.

Commit changes and push to `main` to publish. Check the Pages deployment in [Actions](https://github.com/jakeboxer/Dropshot-releases/actions), then verify the public site at <https://jakeboxer.github.io/Dropshot-releases/>.

See [GitHub's publishing-source documentation](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site).

## Scope

This initial page has no download link. Upload app binaries as GitHub Release assets before adding one. Custom domains, visual design, and an update feed are later work.
