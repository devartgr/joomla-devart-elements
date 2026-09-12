# DevArt Elements

Reusable content elements for Joomla 6+.

## Requirements

- Joomla 6.0+
- PHP 8.3.0+

## Package

Version `1.1.5` contains:

- `com_devartelements` — administrator component (source of truth for element records)
- `mod_devartelements` — frontend module renderer for one published element

Element families: Content Blocks, Navigation, Data, Media, and Pricing.

### Highlights since 1.1.3

- **Hover Blocks** — color tiles with optional icon, title/link and photo on hover (no title plate)
- **Footer Menu** — up to 4 link columns (icon, title, URL, same/new window)
- **Photo Slider** — landscape row, hover icon, lightbox, auto-slide, mobile 1-up
- **Navigation Bar** — full site header (logo, Joomla menu, social, custom text, top bar, mobile chrome, overlay placement)
- Content Blocks: Simple Content, Button, Testimonials, Team, Logo Cloud, Alert / Notice

## Install / Update

1. Install or update `pkg_devartelements_v1.1.5.zip` from [Releases](https://github.com/devartgr/joomla-devart-elements/releases).
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
