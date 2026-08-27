# Changelog

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
