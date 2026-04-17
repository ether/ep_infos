# Pad Info for Etherpad

## Installation

Install from the Etherpad admin UI (**Admin → Manage Plugins**,
search for `ep_infos` and click *Install*), or from the Etherpad
root directory:

```sh
pnpm run plugins install ep_infos
```

> ⚠️ Don't run `npm i` / `npm install` yourself from the Etherpad
> source tree — Etherpad tracks installed plugins through its own
> plugin-manager, and hand-editing `package.json` can leave the
> server unable to start.

After installing, restart Etherpad.
