# Changelog

## 1.1.5 (2026-09-12)

### Added — Content
- **Hover Blocks**: color tiles with optional icon, title/link and photo on hover.
- Title overlays the color/photo with **no background plate**; flush grid, optional gap and full-width.

### Requirements
- Joomla 6.0+
- PHP 8.3.0+

## 1.1.4 (2026-09-12)

### Added — Navigation
- **Footer Menu**: up to 4 columns with heading + link items (icon, title, URL, same/new window).
- Uppercase styling, hover underline and optional title tooltips for long labels.

### Added — Media
- **Photo Slider**: single-row photos with optional titles, hover icon, lightbox popup and auto-slide.
- Pause on hover, configurable visible count, reduced-motion safe behaviour.

### Fixed
- Footer Menu admin form: replaced nested required subforms with four clear column groups on the Content tab so Save works.
- Photo Slider: landscape 16:9 frames (was portrait), responsive lightbox, and one photo at a time on mobile.

### Requirements
- Joomla 6.0+
- PHP 8.3.0+

## 1.1.3 (2026-09-07)

### Added — Navigation Bar (highlight)
- Full site **Navigation Bar**: logo, Joomla menu, social icons, custom text and
  optional top bar.
- Placement modes: **block** or **overlay** for use above slider/hero content.
- Layout groups for **Slot positions** and **Top bar**; optional horizontal divider.
- Mobile chrome: centered logo (width %), independent social/custom placement,
  and custom mobile colors.
- Styling depth: RGBA pickers (opacity + transparent) for submenu, bar and mobile
  chrome backgrounds; custom menu/text rem sizes, line heights and colors.
- Themes: default **Gray** with transparent bar; **None** seeds custom colors from
  the previous named theme; optional logo max width/height limits; active menu
  color when theme is None.

### Added — Content Blocks
- **Simple Content**: title, created date, lead, main, sub content, read more;
  sizes from extra small to XX large plus custom rem; themes and custom colors
  (no backgrounds).
- **Button**: solid / outline / soft / ghost / link styles, sizes, themes, Font
  Awesome icon and full custom colors.
- **Testimonials**: quote, author, role, avatar and optional rating.
- **Team**: member cards with photo, role, bio and optional profile link.
- **Logo Cloud**: partner/client logos with optional links and grayscale hover.
- **Alert / Notice**: lightweight page announcements with info / success /
  warning / danger tones.

### Requirements
- Joomla 6.0+
- PHP 8.3.0+

## 1.1.2 (2026-09-01)

### Added
- Navigation **Dropdown Menu** element: horizontal menu with dropdown submenus,
  either from a selected Joomla menu or custom manual items with nested children.
- Responsive mobile menu toggle, hover/click submenu trigger, DevArt color themes.
- Data **Feature Blocks** element: full-width column grid with icon, subtitle,
  title and read-more link with underline; per-item DevArt themes; Font Awesome
  icon picker in administrator.

### Changed
- **Copyright** and **Branding**: color theme now styles accent, text and links
  (not background tint only).
- **Copyright** and **Branding**: new Background option — None or Theme color.

### Fixed
- **Feature Blocks**: theme backgrounds use visible DevArt pastel tints
  (red, orange, blue, green, yellow, purple, gray, dark).

### Requirements
- Joomla 6.0+
- PHP 8.3.0+

## 1.1.1 (2026-08-31)

### Fixed
- Clean install now creates `#__devartelements_elements`: install/uninstall SQL
  manifests use `charset="utf8"` as required by Joomla’s installer (previously
  `utf8mb4` caused the SQL files to be skipped entirely).
- Schema update `1.1.1.sql` recreates the full elements table with
  `CREATE TABLE IF NOT EXISTS` so sites that installed `1.1.0` without the
  table can repair via package update or Database → Update Structure.

### Requirements
- Joomla 6.0+
- PHP 8.3.0+

## 1.1.0 (2026-08-27)

First public release after `1.0.1`. Intermediate private builds `1.0.2`–`1.0.12`
are not published separately; their verified changes are included here.

### Added
- Fifteen locales for administrator, module and package (`en-GB`, `el-GR` curated;
  fr-FR, de-DE, es-ES, it-IT, pt-BR, cs-CZ, nl-NL, pl-PL, ru-RU, uk-UA, ja-JP,
  tr-TR, zh-CN).
- Administrator hub dashboard (Content Blocks / Navigation / Data / Media /
  Pricing / Tools) with Options and Modules shortcuts.
- Lightweight ArticleSelect picker for large article sites (replaces slow
  Joomla `modal_article`).
- Module output cache clearing after element save and import.
- Shared language keys for admin forms and frontend Read more / Open page /
  media controls.

### Changed
- ElementFamilyHelper consolidated: component is the single source of truth;
  module uses a thin site facade.
- Module configuration uses only the unified `element_id` selector (legacy
  per-type hidden fields removed).
- Accordion titles wrap responsively on desktop and mobile.

### Fixed
- Import HTML sanitization for stored XSS in `content_json`.
- Upload validation with `is_uploaded_file()` on import preview.
- Strict JSON encode/decode in ElementModel with user-facing errors.
- ElementTable title requirement and unique type+alias validation.
- URL `filter="url"` on admin URL fields.
- Schema checker false positive from non-Joomla `IF NOT EXISTS` SQL syntax.

### Security
- Import path sanitizes non-URL strings in `content_json` via Joomla InputFilter.
- Rejects non-upload file paths during import preview.

### Requirements
- Joomla 6.0+
- PHP 8.3.0+

## 1.0.1

Previous public release.

## Earlier private builds (not published)

`1.0.2`–`1.0.12` were internal milestones only and are folded into `1.1.0`.
