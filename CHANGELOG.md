# Changelog

## 1.2.2 (2026-10-25)

### Improved — Navigation Horizontal Menu
- Nested submenus with Max depth (3+ levels) without dropping later top-level items.
- Submenu expand direction: **Down** or **Right (flyout)**.
- Active/hover style: text-only or **Gantry-like background**.
- Optional open-on-hover; click still works on touch / when hover is off.
- Custom items support nested children (up to 3 form levels).

### Improved — Navigation Bar
- Submenu expand direction: **Down** or **Right (flyout)** (Menu tab).
- Active/hover style: text-only or **Gantry-like background** (Menu tab).
- Active background height: **Padded** or **Full height** (Gantry bar fill).
- Mobile panel: **Off-canvas left/right** (Gantry-style body-portaled full-height drawer + backdrop) or Fade; close (X) control; nested items open on tap only; resize resets open state.
- Off-canvas link styles reset after portal (no UA grey buttons / white-on-light text); caret spacing improved.
- Full-height Gantry highlight is edge-to-edge without inflating the bar height.
- Navbar desktop submenu width: Auto / Compact / Medium / Wide / Custom (px).
- Max menu items limits top-level only; nested items load within Max depth.
- Submenu Gantry highlight no longer inherits top-bar colours; multi-line submenu labels left-align with caret on the first line.
- Submenu Gantry hover no longer loses label contrast on colour themes (cascade overrode text colour to match the fill).

### Fixed — Navigation
- Navbar / Dropdown menu loading no longer SQL-limits the full tree by `lft` (deeper max depth no longer hides later top items).
- Navbar submenu JS keeps ancestor panels open when opening nested levels; nested panels fly to the right by default.

### Requirements
- Joomla 6.0+
- PHP 8.3.0+

## 1.2.1 (2026-10-24)

### Added — Navigation
- **Horizontal Menu**: clean single-row link bar from a Joomla menu or custom items.
- Classic DevArt colour themes (red / orange / blue / green / yellow / gray / dark) plus custom colours.
- Solid or transparent background, font size presets/custom rem, item spacing, uppercase, hover underline, optional Font Awesome icons (custom items), full module width, and active-item highlighting for Joomla menu sources.

### Requirements
- Joomla 6.0+
- PHP 8.3.0+

## 1.2.0 (2026-10-04)

### Security
- URL cleaner: strip control characters; allow only `http` / `https` / `mailto` / `tel`.
- Reject protocol-relative URLs (`//host`) in links and media paths.
- Frontend HTML filter: explicit whitelist (no `style`, no `iframe`).
- Article-backed FAQ/Tabs/Accordion: require published category + category access.
- Admin icon field preview: safe DOM / `textContent` (no raw `innerHTML`).

### Fixed
- Import commit: validate preview payload inside try/catch (no uncaught 500).
- Article images go through `UrlHelper::cleanMedia()`.
- Menu-backed Accordion / Dropdown / Navbar / Tabs: filter by publish window, access, and language (like core `mod_menu`); resolve alias / URL / heading / separator item links correctly.
- Module `cachemode` changed from `static` to `itemid` (keyed by Itemid + view levels). Default module caching remains OFF.
- Import preview no longer stores the full JSON payload in the session (tmp file + small session token; 1-hour expiry).
- Import alias uniqueness uses one alias-index query instead of a COUNT per row.
- Duplicate: require `core.edit` + element access, limit 50, restore request family/mode, surface save failures; one cache clear after the batch.
- Import skips rows with unknown access/language instead of silently remapping to Public / All languages.
- Import alias index loads only the element types present in the import file.
- Element picker modal validates its GET CSRF token; unpublished rows show a badge; module field is read-only without `core.manage`.
- Cache clear failures are logged via `LogHelper` (still never block saves).
- Export `extension_version` comes from the installed component manifest (not a hard-coded string).
- Import validates access/language against site view levels and content languages; inserts in chunks; preview summary stays in session (no full-file decode on Tools view).
- Import/export errors write to `com_devartelements.log.php` via a dedicated logger.
- Database index `idx_family_ordering` (`family`, `ordering`) for the administrator Elements list query.
- `scripts/validate.php` requires `joomla.asset.json` version to match the package and resolves asset URIs the Joomla way (`com_devartelements/file.css` → `media/.../css/file.css`).

### Changed
- Frontend module template split into per-type partials under `tmpl/types/` (no intended behavior change).
- `ElementTypeConfig` holds per-type `content_json` key whitelists and required-field checks; `ElementModel::save()` delegates to it (no intended behavior change).
- Module Dispatcher type preparator dispatch uses `match` instead of an if-chain (no intended behavior change).

### Added
- **Split Slider**: optional auto slide (interval + pause on hover).
- **Split Slider**: optional full module width (edge-to-edge).
- **Full module width** option on section-like elements: FAQ, Tabs, Accordion, Navbar, Footer Menu, Counter, Countdown, Statistics, Chart, CTA, Banner, Hero, Simple, Testimonials, Team, Logos, Alert, About, Branding, Photo Slider, Audio, Video, Pricing, Comparison (plus existing Blocks / Hover / Fade / Gray / Icon / Push / Split / Image).
- Caching / Cloudflare operator guide: `docs/caching.md`.
- Element save/import also clears the Joomla `page` cache group (in addition to module groups).
- Module element picker: lightweight modal search (replaces the SQL dropdown that loaded every published element).

### Upgrade warnings
- Protocol-relative URLs (`//example.com/...`) are rejected in structured URL/media fields (`UrlHelper`). Links inside rich-text HTML still pass through the HTML whitelist filter and are not rejected solely for using `//`.
- Inline `style` attributes and `iframe` embeds in element HTML are stripped on frontend render.
- Newly added full-width switches (FAQ/Tabs/CTA/Hero/…, Split Slider, Photo Slider, etc.) default OFF; enable explicitly when needed. Legacy modules that already had full width (Blocks, Hover/Fade/Gray Blocks, Icon Slider, Push Slider) keep their previous default-ON behavior.
- PHP 8.3 / 8.4 / 8.5 compatibility targets verified locally (CLI + Herd runtime); see `qa/checklist.md`.

### Requirements
- Joomla 6.0+
- PHP 8.3.0+

## 1.1.10 (2026-09-24)

### Changed — Joomla 7 forward compatibility
- **ElementTable**: uses `getDatabase()` instead of the protected `$_db` property (alias uniqueness checks).
- **Module content prepare**: dispatches `ContentPrepareEvent` instead of legacy `triggerEvent`.
- **Element edit form**: loads `form.validate` and `keepalive` via WebAssetManager (no HTMLHelper `behavior.*`).
- **Module ElementFamilyHelper**: boots the component namespace with `bootComponent()` instead of `require_once`.

### Requirements
- Joomla 6.0+
- PHP 8.3.0+

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
