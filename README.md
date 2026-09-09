# PFL / MVP 2027 betting sponsorship

Two one-pagers in a single tabbed page: Cloudbet structure (branded) and market approach (unbranded).

## Assets

| File | What it is | Used by | Notes |
|---|---|---|---|
| `index.html` | The page. Both tabs, all styling and the tab script inline. | — | Single file, no build step. |
| `assets/favicon.svg` | Browser tab icon. | `index.html` head | Placeholder PFL mark. Replace with the real logo. |
| `assets/cloudbet.png` | Cloudbet wordmark, black on transparent, 693 × 58. | Cloudbet tab masthead | Cropped from the supplied JPEG. Do not add to the market approach tab. |

External dependency: Archivo, loaded from Google Fonts. The page falls back to Helvetica or Arial if it is blocked.

## Repo layout

```
/
├─ index.html
└─ assets/
   ├─ favicon.svg
   └─ cloudbet.png
```

## Publishing

1. Push to the repo root on `main`.
2. Settings → Pages → Source: Deploy from a branch → `main` / `/ (root)`.
3. Live at `https://<user>.github.io/<repo>/`.

## Swapping the favicon

Drop the real PFL mark in as `assets/favicon.svg`, or use a square PNG and change the head link:

```html
<link rel="icon" type="image/png" href="assets/favicon.png">
```

## Adding an operator logo

Logos go on the branded tab only. Crop to the mark, remove the background, save as PNG to `assets/`, then reference it in the masthead:

```html
<div class="mast-logo">
  <img src="assets/<operator>.png" alt="<Operator>">
  <span>Incumbent global betting partner</span>
</div>
```

Sizing is handled by CSS at 22px height, so any width works.

## Editing content

Each section is a `.block`. Numbered blocks on the Cloudbet tab also carry `.numbered`. Red callouts are `<p class="note">`. Brand colours sit in `:root` at the top of the style block.

## Notes

- Draft for internal discussion. Not cleared for external circulation.
- Printing hides the tabs and outputs both one-pagers, one per page.
