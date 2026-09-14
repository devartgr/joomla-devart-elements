# DevArt Elements

Reusable content elements for Joomla 6+.

## Requirements

- Joomla 6.0+
- PHP 8.3.0+

## Package

Version `1.1.6` contains:

- `com_devartelements` — administrator component (source of truth for element records)
- `mod_devartelements` — frontend module renderer for one published element

Element families: Content Blocks, Navigation, Data, Media, and Pricing.

### Highlights in 1.1.6

- **Push Slider** — vertical push slides: sharp left photo, blurred right overlay with title/subtitle/text/button
- **Split Slider** — title list left, photo right; theme active state and + hover
- **Fade Blocks** — stacked photo→text fade rows (themes, title sizes, full width)
- **Grayscale Blocks** — grayscale until hover/focus, then color + themed title bar (poster/landscape)

### Also included since 1.1.3

- **Hover Blocks**, **Footer Menu**, **Photo Slider**, **Navigation Bar**
- Content Blocks: Simple Content, Button, Testimonials, Team, Logo Cloud, Alert / Notice

## Install / Update

1. Install or update `pkg_devartelements_v1.1.6.zip` from [Releases](https://github.com/devartgr/joomla-devart-elements/releases).
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
