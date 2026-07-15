# front-assets-cdn

Binary 3D/media asset library for the [`front`](https://github.com/diegonmarcos/diegonmarcos.github.io) monorepo.
Keeps GLBs, textures, and HDRIs out of the site repos so clones stay lean.

## Layout

Mirrors `front/` exactly — an asset for project `X` lives at the same relative path it
would under `front/X/static/`:

```
a-Companies/leafy-2/static/assets/
  models/          # characters, fauna (GLB)
  models/nature/   # Quaternius Ultimate Stylized Nature Pack (GLB)
  textures/        # ground, water, PBR maps
  space/           # planet / sky textures
```

## Served via jsDelivr (CDN)

Any file is globally CDN-served, CORS-enabled, free:

```
https://cdn.jsdelivr.net/gh/diegonmarcos/front-assets-cdn@main/<path>
```

Consumed as a git submodule of `front` (versioned + offline-buildable); the live sites
load by jsDelivr URL. Note: jsDelivr caches `@main` ~12h — purge via
`https://purge.jsdelivr.net/gh/diegonmarcos/front-assets-cdn@main/<path>` after updates,
or pin a commit SHA instead of `@main`.

## Licenses

- **Nature pack** (`models/nature/`): Quaternius — *Ultimate Stylized Nature Pack*, CC0.
- **Fauna / characters** (`models/`): three.js examples + Quaternius (poly.pizza), CC0 / CC-BY.
- **Textures**: Poly Haven (CC0), three.js (MIT).

Per-asset provenance is tracked in each project's `assets.json` catalog (license/author/source).
