# Changelog

## 1.1.9 (2026-09-21)

### Added — Content
- **Icon Slider**: carousel of icon / title / intro / read more cards with per-card hover colour, full module width and autoplay.

### Added — Media
- **Audio Player**: progress / seek bar while playing (scrub forward and back).

### Fixed
- Video Block: removed the false required warning on the MP4 media field after a file is selected.
- Icon Slider: idle title and intro use dark text (white only on hover), including against template module colour schemes.

### Changed
- Admin icon browser: expanded curated Font Awesome Free solid and brands set (shared by all Font Awesome icon fields).

### Requirements
- Joomla 6.0+
- PHP 8.3.0+

## 1.1.8 (2026-09-15)

### Added — Media
- **Image Block**: full module width option on the Display tab.

### Fixed — Media
- Image Block: removed the false required warning on the image media field after an image is selected.

### Requirements
- Joomla 6.0+
- PHP 8.3.0+

## 1.1.7 (2026-09-15)

### Added — Media
- **Photo Slider**: rising hover effect on photos.
- **Photo Slider**: configurable gap between photos (none / small / medium / large).

### Changed / Fixed — Media
- Photo Slider: smoother infinite loop when restarting after the last photo.
- Photo Slider: drop shadow corrected (no longer clipped by overflow).
- Photo Slider: reliable visible-count and gap layout via JS pixel sizing.

### Requirements
- Joomla 6.0+
- PHP 8.3.0+

## 1.1.6 (2026-09-14)

### Added — Media
- **Split Slider**: two-column layout — title list on the left, one photo on the right.
- Active item shows classic DevArt theme background and subtitle; hover shows a + icon.
- Keyboard navigation (arrows / Home / End) and reduced-motion safe image swap.
- **Push Slider**: vertical push slides — sharp photo left, blurred photo + light overlay right.
- Push Slider content: large title sizes (presets/custom rem), subtitle, text and themed button.
- Push Slider controls: up/down arrows, dots, keyboard and vertical swipe.

### Added — Content
- **Fade Blocks**: stacked image/text rows — photo left with fade into themed text column (title, subtitle, text, icon link).
- Classic DevArt themes (default **Dark**), title size presets/custom rem, optional full module width and dividers.
- **Grayscale Blocks**: photo columns stay grayscale until hover/focus, then reveal color with a themed title bar.
- Poster / Landscape rectangular ratios, white inactive titles, columns, gap and full module width.

### Fixed
- Split Slider: active subtitle and title wrap inside the left column instead of overflowing under the photo.

### Requirements
- Joomla 6.0+
- PHP 8.3.0+

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
