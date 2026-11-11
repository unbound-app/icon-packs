# Icon packs

First-party icon packs for [Unbound](https://unbound.rip). Install them from the [store](https://unbound.rip/addons/icons).

This repository is a submodule of [marioparaschiv/unbound](https://github.com/marioparaschiv/unbound) at `packages/icon-packs`. Its publish workflow releases every pack whose `manifest.json` version is newer than the live one, and the store keeps its own copy of each released version.

## Pack layout

```
hugeicons/
├── manifest.json   id, name, description, authors, version, icon, type: "icon-pack", main: "icons.json"
├── ADDON.md        the store page
├── CHANGELOG.md    one entry per version
├── LICENSE
├── design/components/Icon/native/redesign/generated/images/
│   └── SettingsIcon@3x.png   one image per Discord asset, at @2x or @3x
└── images/native/icons/
    └── ic_gear@3x.png        older Discord icons, already coloured
```

Image paths copy Discord's asset paths without the leading `/assets/`. `icons.json` and the `assets` field of the manifest are written at publish time; do not commit them.

## Releasing a pack

1. Add or change images, then bump `version` in the pack's `manifest.json` and add a `CHANGELOG.md` entry.
2. Push to `main` here.
3. In marioparaschiv/unbound, move the submodule to the new commit: `git -C packages/icon-packs pull && git add packages/icon-packs`, and merge that to `main`.
