# DevArt Polls — Translations

English (`en-GB`) is the source language for all extension strings.

## Supported Languages

| Language | Tag | Frontend | Administrator | Status |
|----------|-----|----------|---------------|--------|
| English | `en-GB` | Yes | Yes | Source language |
| Greek | `el-GR` | Yes | Yes | Machine-generated; review welcome |
| French | `fr-FR` | Yes | Yes | Native review by easysiteshop.com (V2, August 2026) |
| German | `de-DE` | Yes | Yes | Machine-generated; review welcome |
| Spanish | `es-ES` | Yes | Yes | Machine-generated; review welcome |
| Italian | `it-IT` | Yes | Yes | Machine-generated; review welcome |
| Brazilian Portuguese | `pt-BR` | Yes | Yes | Machine-generated; review welcome |
| Czech | `cs-CZ` | Yes | Yes | Machine-generated (Argos + Google fallback); review welcome |
| Dutch | `nl-NL` | Yes | Yes | Native review by Jip Jonker (October 2026) |
| Polish | `pl-PL` | Yes | Yes | Machine-generated (Argos + Google fallback); review welcome |
| Russian | `ru-RU` | Yes | Yes | Machine-generated (Argos + Google fallback); review welcome |
| Ukrainian | `uk-UA` | Yes | Yes | Machine-generated (Argos + Google fallback); review welcome |
| Japanese | `ja-JP` | Yes | Yes | Machine-generated (Argos + Google fallback); review welcome |
| Turkish | `tr-TR` | Yes | Yes | Machine-generated (Argos + Google fallback); review welcome |
| Chinese (Simplified) | `zh-CN` | Yes | Yes | Machine-generated (Argos + Google fallback); review welcome |

## Contributors

### French (`fr-FR`)

**easysiteshop.com** — native French review and administrator translation (August 2026).

Latest review package: **Translations V2** (23 August 2026), with additional administrator and module updates integrated in **1.2.6** (August 2026).

Covers:

- `com_devartpolls` administrator and site language files
- `mod_devartpoll` frontend module language files
- Package installer language file

Corrections and improvements are welcome through GitHub.

### Dutch (`nl-NL`)

**Jip Jonker** — native Dutch review (October 2026), based on DevArt Polls 1.2.11.

Integrated in **1.2.12**. Consistent terminology: poll = peiling, survey = enquête, informal register (“je”).

Covers:

- `com_devartpolls` administrator and site language files
- `mod_devartpoll` frontend module language files
- Package installer language file

Corrections and improvements are welcome through GitHub.

## Generation Workflow

Machine-generated locales are produced from `en-GB` with:

1. `scripts/i18n/translate-ini.py` — Argos Translate first, Google GTX fallback
2. Placeholder and technical-token protection (`%s`, `%d`, `vote.refresh`, etc.)
3. `scripts/i18n/validate-ini.php` — key parity, placeholder parity and protected-token checks
4. `scripts/i18n/repair-email-otp-body.php` — single-line repair for multiline email OTP body strings when needed

Protected locales such as `fr-FR` are never overwritten by the generator.

## Notes

- Placeholders (`%s`, `%d`, HTML fragments) must remain unchanged in every translation.
- Technical tokens such as `vote.refresh` must remain untranslated.
- Administrator and frontend translations for machine-generated locales are open to native-speaker review.
- Translation-only milestones must not alter PHP, JavaScript, CSS, SQL, or voting logic.
