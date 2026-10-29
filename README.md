# DevArt Elements

Reusable content elements for Joomla 6+.

## Requirements

- Joomla 6.0+
- PHP 8.3.0+

## Package

Version `1.2.8` contains:

- `com_devartelements` — administrator component (source of truth for element records)
- `mod_devartelements` — frontend module renderer for one published element

Element families: Content Blocks, Navigation, Data, Media, and Pricing.

### Highlights in 1.2.8

- **Stage Slider** — large single-image stage with progress bar, dots, arrows and theme accent
- CSS-only transition effects (fade, slide, zoom, wipe, blur, flip) with duration presets
- Full module width, aspect-ratio or fixed height, optional max width, optional lightbox

### Also in 1.2.7

- **Collage Slider** — Gantry Showcase-style overlapping 4-photo groups with fixed layout (570×760 / 570×426 frames)
- Desktop: up/down arrows left of the collage, drop shadows, optional dots, lightbox, autoplay
- Mobile: sequential slides — photos 1–3 alone, photo 4 with text/CTA card, then next group
- Live Blog domain hint uses generic `domain.gr` example

### Also in 1.2.6

- **Live Blog Banner** — LIVE badge with blinking dot, article title (optional custom headline), share buttons
- Optional article date (created/modified as `d/m/Y H:i`) and Google News CTA (`preferences/source?q=` + domain)
- White headline without underline; news247-style padding; compact mobile LIVE pill

### Also in 1.2.5

- **Social Icon Bar** — horizontal/vertical bar with preset networks, auto-filled icons, sizes, spacing, shapes
- Colour styles: original brand colours, DevArt theme, or uniform mono

### Also in 1.2.4

- **Footer Menu** — optional column headings; link URLs stored as entered (no site-root prefix)
- Footer Menu Display: divider lines, font size, vertical item spacing

### Also in 1.2.3

- **Navbar** — parent items with a real menu URL stay clickable links; caret toggles the submenu
- Navbar caret chevron size restored

### Also in 1.2.2

- **Horizontal Menu** — nested submenus, expand down/right, Gantry-like active background
- **Navigation Bar** — same expand + Gantry styles; full-height highlight; off-canvas mobile drawer with close control
- Navbar desktop submenu width presets (Auto / Compact / Medium / Wide / Custom)
- Tree-loading fix so deeper max depth no longer hides later top-level items

### Also in 1.2.1

- **Horizontal Menu** — clean single-row link bar from a Joomla menu or custom items
- Classic colour themes, custom colours, solid or transparent background
- Font size, spacing, uppercase, hover underline, optional icons, full module width

### Also in 1.2.0

- **Security** — stricter URL/media cleaning, protocol-relative URL rejection, frontend HTML whitelist, safer icon preview
- **Split Slider** — optional auto slide and full module width
- **Full module width** on remaining section-like element types
- **Import / export / duplicate** hardening · module element picker · maintainability refactor

### Also in 1.1.10

- **Joomla 7 forward compatibility** — `getDatabase()`, `ContentPrepareEvent`, WebAssetManager form assets, `bootComponent()` (no `require_once`)

### Also in 1.1.9

- **Icon Slider** — icon / title / intro / read more cards with per-card hover colour, full width and autoplay
- **Audio Player** seek bar · Video MP4 required-field fix · expanded admin icon browser

### Also in 1.1.8

- **Image Block** — full module width; fixed false required warning after selecting an image

### Also in 1.1.7

- **Photo Slider** polish — rising hover, configurable gap, smoother infinite loop, corrected drop shadow

### Also in 1.1.6

- **Push Slider**, **Split Slider**, **Fade Blocks**, **Grayscale Blocks**

### Also included since 1.1.3

- **Hover Blocks**, **Footer Menu**, **Navigation Bar**
- Content Blocks: Simple Content, Button, Testimonials, Team, Logo Cloud, Alert / Notice

## Install / Update

1. Install or update `pkg_devartelements_v1.2.6.zip` from [Releases](https://github.com/devartgr/joomla-devart-elements/releases).
2. Or use Joomla’s extension update server (configured in the package manifest).

## Documentation

- [CHANGELOG.md](CHANGELOG.md)
- [AGENTS.md](AGENTS.md) — repository standards
- [PROJECT_STATUS.md](PROJECT_STATUS.md) — operational status
- `docs/` — architecture and baseline notes
- `qa/checklist.md` — Joomla QA checklist

## Development

`source/` is the only development source. Generated packages belong under `builds/`. Official packages are copied to `releases/`.

```shell
php scripts/validate.php
php scripts/build.php
```

## License

GNU General Public License version 3 or later.
