# ep_infos

GitHub Pages source for **<https://etherpad.org/ep_infos/>**.

This is **infrastructure**, not an installable Etherpad plugin — the `ep_` prefix is misleading. Don't try to `pnpm run plugins install ep_infos` (the package isn't on npm, and there's no plugin code in this repo).

## What it does

`.github/workflows/build-web-infos.yaml` runs daily at 01:00 UTC (and on `workflow_dispatch`):

1. Downloads `info.json` and `plugins.json` from `static.etherpad.org`.
2. Bundles them as a GitHub Pages artifact.
3. Deploys to <https://etherpad.org/ep_infos/>.

That's it. The result is a freshly mirrored copy of the plugin/info JSON for anyone (or any tool) that prefers fetching from the `etherpad.org` apex domain over `static.etherpad.org`.

## Updating

To force a refresh outside the daily cron, run the workflow manually:

```sh
gh workflow run build-web-infos.yaml -R ether/ep_infos
```
