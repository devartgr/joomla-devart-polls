# DevArt Polls for Joomla

Polls and surveys for Joomla 6, designed for production websites that need anonymous voting, Joomla article-backed answers, cache-safe frontend rendering, and simple survey response handling.

![Joomla](https://img.shields.io/badge/Joomla-6.x-blue)
![PHP](https://img.shields.io/badge/PHP-8.3%2B-green)
![Release](https://img.shields.io/badge/Version-1.3.2-orange)
![License](https://img.shields.io/badge/License-GPLv2%2B-red)

---

## Overview

DevArt Polls is a Joomla 6 package with:

- `com_devartpolls` — administrator component
- `mod_devartpoll` — frontend module

It supports two product modes:

- **Poll** — one question, anonymous voting, aggregate results
- **Survey** — multiple questions, stored responses, response manager, CSV export

Question types are limited to **single choice** and **multiple choice**.

The extension is built for Joomla 6, PHP 8.3+, Full Page Cache, and Cloudflare-friendly frontend behaviour.

---

## Version 1.3.2

Native Dutch (`nl-NL`) update by Jip Jonker for the 1.3.1 Results strings and
remaining English leftovers from the 1.3.0 train, plus a cosmetic fix for the
duplicate Empty trash toolbar button in the Polls Trashed filter. Safe update
from 1.3.1. See `CHANGELOG.md`.

### Requirements

- Joomla 6.0+
- PHP 8.3+

---

## Version 1.3.1

Administrator Results view for poll and survey vote totals (independent of
frontend Show Results), with totals CSV export and entry points from the Polls
list and poll edit toolbar. Safe update from 1.3.0. See `CHANGELOG.md`.

---

## Version 1.3.0

DevArt Polls 1.3.0 is the public stabilisation release after the private post-1.2.12
improvement train. Intermediate private package numbers are not listed.

### Highlights

- Cache-safe voting under Full Page Cache / Cloudflare, with Dashboard cache check
- Hardened verified-email OTP and poll-row locking / post-lock vote revalidation
- Article-backed answers, Guest/Registered duplicate pairing, Responses list improvements
- Expanded locales; SEF-aware Cloudflare Bypass guidance
- Safe update from the last public package DevArt Polls 1.2.12

---

## Version 1.2.12

DevArt Polls 1.2.12 integrated a native Dutch (`nl-NL`) translation review by
Jip Jonker and removed a colliding administrator language key for Survey
Responses vs Participants.

### Highlights

- Native Dutch (`nl-NL`) review by Jip Jonker (peiling / enquête / “je”)
- Administrator `.sys.ini` no longer overrides Participants with Survey Responses
- Safe update from DevArt Polls 1.2.11

### Requirements

- Joomla 6.0+
- PHP 8.3+

### Safe update

Safe update from DevArt Polls 1.2.11. No database schema changes.

---

## Version 1.2.11

DevArt Polls 1.2.11 fixed Messages tab custom text saving, the Survey Response
Storage `counters_only` editor overwrite, and related low-risk
correctness/security polish.

### Highlights

- Messages tab custom texts save and reload correctly
- Survey `counters_only` is preserved when reopening the editor
- Unexpected vote errors return a generic visitor message
- Safe update from DevArt Polls 1.2.10

### Requirements

- Joomla 6.0+
- PHP 8.3+

### Safe update

Safe update from DevArt Polls 1.2.10. No database schema changes.

---

## Version 1.2.9

DevArt Polls 1.2.9 added Display Options Layout (List / Cards) with optional
column counts per device. Results boards are unchanged. The Theme group title
display bug is fixed.

### Highlights

- **Options Layout**: List (default) or Cards on the Display tab
- Cards columns for phone, tablet and desktop containers
- Vote form only — results boards keep their existing layout
- Fixed administrator label **Theme and size** (no literal `&amp;`)

### Requirements

- Joomla 6.0+
- PHP 8.3+

### Safe update

Safe update from DevArt Polls 1.2.8. No database schema changes.

---

## Version 1.2.8

DevArt Polls 1.2.8 added Poll Results Order (By votes / Administrator order).
Survey results keep the administrator order. The vote form is never reordered.

### Highlights

- **Results Order** setting on the Results tab (By votes / Administrator order)
- Poll results can show the leader first; Surveys keep fixed admin option order
- Vote form option order unchanged
- Safe update from DevArt Polls 1.2.7 — no database schema changes

---

## Version 1.2.7

DevArt Polls 1.2.7 fixed the Reset Results /
Reset Protection Locks TypeError and improves thank-you / already-voted
confirmation placement after voting.

### Highlights

- Fixed administrator reset actions Input type hint for Joomla 6
- Thank-you and already-voted messages appear below results on long polls
- Confirmation status scrolls into view after AJAX vote refresh
- Safe update from DevArt Polls 1.2.6 — no database schema changes

---

## Version 1.2.6

DevArt Polls 1.2.6 fixed verified email OTP
expiry validation on non-UTC PHP timezones (for example Europe/Paris), where
fresh codes were incorrectly rejected as expired.

### Highlights

- Timezone-safe OTP expiry comparison using Joomla `Date` in UTC
- **Reset Protection Locks** administrator action for clearing email/cookie/visitor duplicate locks without wiping vote counters (testing/staging)
- Latest easysiteshop.com French administrator and module review updates
- Safe update from DevArt Polls 1.2.5 — no database schema changes

---

## Version 1.2.5

DevArt Polls 1.2.5 added PHP 8.4/8.5 captcha
compatibility fixes, article picker improvements, a redesigned administrator
dashboard hub, Display tab fieldset grouping, eight additional languages, and
JED Checker–compatible quoted language INI values.

### Highlights

- PHP 8.4/8.5 captcha hostname validation compatibility
- Article picker category filter and prefix title search for large content tables
- Redesigned administrator dashboard hub with action cards and Modules shortcut
- Display tab grouped into bordered fieldsets (theme, answer images, header, footer)
- Machine-generated translations for Czech, Dutch, Polish, Russian, Ukrainian, Japanese, Turkish, and Chinese Simplified
- French (`fr-FR`) translations reviewed by easysiteshop.com (unchanged in this release)
- JED Checker–compatible quoted language INI values for all machine-generated locales
- Safe update from DevArt Polls 1.2.4 — no database schema or voting-logic changes

---

## Version 1.2.4

DevArt Polls 1.2.4 added full multilingual admin and frontend coverage for six
languages: English, French, Greek, German, Spanish, Italian, and Brazilian
Portuguese.

### Highlights

- Poll and Survey modes
- Full admin + frontend translations for all supported languages at that time
- Greek (`el-GR`) administrator and frontend translations
- German (`de-DE`), Spanish (`es-ES`), Italian (`it-IT`), Brazilian Portuguese (`pt-BR`) administrator translations
- French (`fr-FR`) translations reviewed by easysiteshop.com
- Machine-generated translations open to native-speaker review
- No PHP, JavaScript, CSS, database, or voting-logic changes

---

## Version 1.2.3

DevArt Polls 1.2.3 added native French administrator translations reviewed by
**easysiteshop.com**, together with updated French frontend strings for the
component site output and frontend module.

---

## Version 1.2.2

DevArt Polls 1.2.2 added frontend translations for French, German, Spanish,
Italian, and Brazilian Portuguese while retaining the Joomla article-backed
answers and refined Questions interface from 1.2.1.

---

## Package Contents

The installable package includes:

- `com_devartpolls` — Polls and surveys component
- `mod_devartpoll` — Frontend poll/survey module

Install or update using the full package only:

`pkg_devartpolls_v1.2.8.zip`

---

## Languages

### Frontend

The component site output and frontend module include:

- English (`en-GB`)
- French (`fr-FR`) — reviewed by easysiteshop.com
- German (`de-DE`)
- Spanish (`es-ES`)
- Italian (`it-IT`)
- Brazilian Portuguese (`pt-BR`)
- Greek (`el-GR`)
- Czech (`cs-CZ`)
- Dutch (`nl-NL`) — reviewed by Jip Jonker
- Polish (`pl-PL`)
- Russian (`ru-RU`)
- Ukrainian (`uk-UA`)
- Japanese (`ja-JP`)
- Turkish (`tr-TR`)
- Chinese Simplified (`zh-CN`)

### Administrator

- English (`en-GB`)
- French (`fr-FR`) — reviewed by easysiteshop.com
- German (`de-DE`)
- Spanish (`es-ES`)
- Italian (`it-IT`)
- Brazilian Portuguese (`pt-BR`)
- Greek (`el-GR`)
- Czech (`cs-CZ`)
- Dutch (`nl-NL`) — reviewed by Jip Jonker
- Polish (`pl-PL`)
- Russian (`ru-RU`)
- Ukrainian (`uk-UA`)
- Japanese (`ja-JP`)
- Turkish (`tr-TR`)
- Chinese Simplified (`zh-CN`)

Non-English translations (except French and Dutch) were generated automatically
and remain open to native-speaker review. Corrections and improvements are
welcome through GitHub. See `docs/translations.md` for contributor credits and
language status.

---

## Product Modes

### Poll

Use Poll mode for one fast anonymous question with aggregate counters and result charts.

### Survey

Use Survey mode when you need:

- Multiple questions
- Stored participant responses
- Administrator response summary
- CSV export

Survey answers can be stored as full responses or aggregate counters, depending on configuration.

---

## Joomla Article-Backed Answers

Each poll or survey answer can use either manually entered content or an
existing Joomla article.

Article-backed answers support:

- Fast bounded article selection without a full result count
- Persistent selected article title and ID
- Automatic editable title and intro-text prefilling
- A 300-character plain-text introduction limit
- Article intro image with full article image fallback
- Compact administrator image previews
- Same-window or new-window article title links
- Joomla publication, access, and language checks on the frontend

Only the answer title is linked to the Joomla article. The answer image and
intro text remain unlinked, and voting remains attached to the existing poll
option ID.

The bounded picker list has been tested on a Joomla site with approximately
230,000 articles. Category filtering and further large-dataset title-search
optimization are planned for a future release.

---

## Frontend Module

Publish the DevArt Poll module on any site position and select a published poll or survey.

The module supports:

- Result display modes
- Chart types and themes
- Optional answer images
- Manual and Joomla article-backed answers
- Optional plain-text answer introductions
- Header and footer text
- Bot protection widgets when enabled

Voting always goes through dedicated dynamic endpoints, even when the page HTML is cached.

---

## Cache and Cloudflare

DevArt Polls is designed for cache-first frontend rendering.

- Page HTML **should** be cached by Joomla or Cloudflare (including Cache Everything)
- Vote JSON endpoints send `Cache-Control: no-store` and must **never** be cached at the edge
- After page load, the module hydrates visitor state and live counters through `vote.refresh`
- Stale "already voted" markup is corrected for the current visitor

HTML cache HIT + uncached vote JSON is the supported production pattern.

### Poll view cache mode (component Options)

Server-side hydrated poll/survey payloads can use:

| Mode | Behaviour |
|---|---|
| **Follow Global Caching** (default) | Uses Global Configuration → System → Cache |
| **Always (poll view only)** | Caches those payloads even when global caching is Off |

Lifetime is still cleared on vote/save. Vote JSON is never stored in this cache.
Use **Always** only when you want poll payload caching while keeping global
Joomla caching Off for the rest of the site.

### Required when you use Cache Everything (or similar)

Vote JSON endpoints send `Cache-Control: no-store`, but that alone is **not a
reliable edge guarantee** when a Cloudflare Cache Rule / Page Rule marks matching
URLs as **Cache Everything** / Eligible for cache. Those rules can still store
vote JSON at the edge and serve another visitor’s refresh/submit response.

**One Bypass Cache Rule is enough** for DevArt Polls. It covers every vote JSON
task (`task=vote.*`) for both SEF Off and typical SEF On URLs. You do not need
separate rules per task.

#### Exact Cache Rule to create

Path: **Caching → Cache Rules → Create rule**

| Field | Exact value |
|---|---|
| Rule name | `DevArt Polls — bypass vote JSON` (any clear name) |
| When incoming requests match | **Custom filter expression** |
| Filter expression | see copy/paste block below |
| Then → Cache eligibility | **Bypass cache** |
| Then → Eligible for cache / Cache Everything | **Do not set** on this rule |

**Expression (copy/paste):**

```text
(
  http.request.uri.query contains "task=vote."
  and (
    http.request.uri.query contains "option=com_devartpolls"
    or http.request.uri.path contains "/component/devartpolls"
    or http.request.uri.path contains "/devartpolls"
  )
)
```

This matches non-SEF (`option=com_devartpolls&task=vote.*`) and typical SEF
routes such as `/component/devartpolls?task=vote.refresh` or menu-based
`/devartpolls?...` paths where `option` is no longer in the query string.

This one expression covers all current vote tasks:

- `vote.submit`
- `vote.refresh`
- `vote.emailOtp`
- `vote.token`
- `vote.powChallenge`

#### Order (important)

Cloudflare **Cache Rules** are stackable: when several rules match and set the
same setting, the **last matching rule wins**.

1. Keep your sitewide **Cache Everything** / Eligible for cache rule.
2. Place the DevArt Polls **Bypass** rule **after / below** Cache Everything.
3. If Bypass is listed **above** Cache Everything, Cache Everything cancels it
   on vote URLs.

Leave Cache Everything enabled for normal HTML pages.

#### Rule limits / OR merge

Cache Rules have plan limits. Prefer **one dedicated Bypass rule** with the
expression above.

If you must save a slot, OR the Polls condition into an **existing Bypass cache**
rule, for example:

```text
(
  (
    http.request.uri.query contains "task=vote."
    and (
      http.request.uri.query contains "option=com_devartpolls"
      or http.request.uri.path contains "/component/devartpolls"
      or http.request.uri.path contains "/devartpolls"
    )
  )
  or
  (/* your other already-bypass conditions */)
)
```

Then keep **Cache eligibility = Bypass cache** on that combined rule.

Never OR the Polls condition into a Cache Everything / Eligible for cache rule.

#### Older Page Rules UI (legacy)

Page Rules use **first match wins** (different from Cache Rules). Put Bypass
**above** Cache Everything. Prefer two URL patterns (or one broad enough match)
so SEF vote URLs are covered:

- `*example.com/*task=vote.*` → Cache Level: Bypass (covers SEF and non-SEF when `task` stays in the query)
- Optionally also `*example.com/*option=com_devartpolls*task=vote.*` if you keep a narrow non-SEF rule

Prefer Cache Rules with the expression above when available.

### How to verify

1. Open a page with a poll → HTML may show `CF-Cache-Status: HIT`.
2. In DevTools → Network, select a `vote.refresh` / `vote.submit` request.
3. Response header must be `CF-Cache-Status: DYNAMIC`, `BYPASS`, or `MISS` — **never** `HIT` with a shared body.
4. Two browsers / private windows must each get their own visitor state after hydrate.

If tests look fine without the rule, you were likely lucky (few concurrent
visitors, cold cache, or CF not yet storing that URL). With Cache Everything and
real traffic, the Bypass rule is **required**, not optional.

---

## Duplicate Protection

Available modes:

- None (testing only)
- Cookie only
- Cookie + IP hash
- Cookie + IP hash + User-Agent hash
- Verified email code

When duplicate protection is enabled, the database enforces `UNIQUE (poll_id, visitor_hash)`.

Guest visitor hashes and signed vote cookies use HMAC (with IPv6 `/64` network
identity). Existing votes and cookies from before that migration still match via
a dual-check. Legacy acceptance is scheduled for removal only after release
`1.4.0` (`VisitorService::LEGACY_HASH_REMOVE_AFTER`). Changing the Joomla
`secret` invalidates current and legacy hashes.

Verified email mode sends a short-lived 6-digit code through Joomla's configured
mailer. Email identities and OTP codes are hashed at rest; plaintext voter email
addresses are not stored. IP is used only to rate-limit OTP requests and is not
used as voter identity or as a duplicate-vote decision.

### Verified Email Voting

Verified email voting is optional and does not require a Joomla user account.

1. The visitor enters an email address.
2. DevArt Polls sends a 6-digit verification code using Joomla's mailer.
3. The visitor enters the code and submits the vote.
4. The same verified email cannot vote again on that poll or survey.

The code expires after 30 minutes, can be used only once, and allows a maximum
of five verification attempts. Resend cooldowns and per-email and per-IP request
limits help prevent automated abuse and excessive email delivery.

Verified email voting enforces **one verified email address = one vote per poll
or survey**. It does not guarantee one physical person per vote because visitors
may have access to multiple or disposable email addresses.

Optional per-poll **Hide Already-Voted Email Disclosure**: when enabled, an OTP
request for an email that already voted returns a generic failure instead of
revealing that the address participated (default off).

---

## Bot Protection

Optional bot protection modes:

- Disabled
- Joomla Proof of Work (mild browser work-factor deterrent — not a full bot shield)
- reCAPTCHA v2
- Cloudflare Turnstile (recommended when you need stronger bot protection)

Bot protection is independent from duplicate protection. Prefer Turnstile or
reCAPTCHA v2 for public high-abuse environments; keep PoW only as a light
automatic option.

---

## Administrator

The component provides:

- Dashboard with totals, status counts, and recent items
- Polls and surveys list
- Poll/survey editor with questions and options
- Numbered answer cards with drag-and-drop and up/down ordering
- Fast Joomla article picker with editable title and intro metadata
- Joomla-native Media Manager selection with image previews
- Survey response summary
- CSV export with formula-injection sanitization
- JSON import/export
- Component options and Joomla ACL

---

## Security

Security measures include:

- Joomla ACL enforcement
- CSRF protection for administrator actions
- Allow-listed administrator list ordering
- Trusted proxy validation for Cloudflare / custom proxies
- Vote return URL hardening
- CSV formula-injection sanitization
- JSON import size, type, and structure limits
- Hashed email identities and one-time verification codes
- OTP expiry, attempt limits, resend cooldown, and request rate limiting
- No plaintext voter email storage
- IP hashes used only for short-lived OTP request rate limiting
- Escaped frontend output
- No `Vary: Cookie` on vote JSON responses

---

## Requirements

- Joomla 6.x
- PHP 8.3 or newer
- MySQL or MariaDB supported by Joomla 6
- A modern browser for administrator and frontend interfaces

---

## Installation

1. Download:

   `pkg_devartpolls_v1.2.8.zip`

2. Open Joomla administrator.

3. Go to:

   `System → Install → Extensions`

4. Upload and install the package.

5. Open:

   `Components → DevArt Polls`

6. Create a poll or survey.

7. Publish a DevArt Poll module and select the item.

---

## Updating

DevArt Polls uses the standard Joomla update system.

Before updating a production website:

- Create a complete backup
- Test on staging
- Verify voting, results, and survey responses
- Clear page cache / CDN cache when necessary

Version 1.2.8 is a safe update from the verified `1.2.7` release. Existing
polls, surveys, questions, options, responses, votes, results, modules,
duplicate-protection modes, and settings are preserved. Existing option IDs
remain stable when answers are reordered.

The package also contains the additive migrations required by earlier stable
releases. Updating a production website should still be tested on staging,
especially when upgrading directly from an older release.

Legacy `email_cookie_ip` settings are automatically converted to the simplified
verified email mode. Obsolete response cookie and IP hashes are cleared without
removing votes.

---

## Download

Latest release:

`pkg_devartpolls_v1.3.0.zip`

GitHub releases:

https://github.com/devartgr/joomla-devart-polls/releases

Direct download:

https://github.com/devartgr/joomla-devart-polls/releases/download/v1.3.0/pkg_devartpolls_v1.3.0.zip

SHA-256:

`8ffa3f6705c50a209a5a7224584623868072b8b6ba5b8f000664e33c4415e3d6`

---

## Support

Project repository:

https://github.com/devartgr/joomla-devart-polls

Website:

https://devart.gr

Before reporting an issue, include:

- Joomla version
- PHP version
- Database type and version
- DevArt Polls version
- Poll or survey mode
- Duplicate protection / bot protection settings
- Relevant error message
- Steps to reproduce

Do not include passwords, private keys, access tokens, or other sensitive information.

---

## License

DevArt Polls is released under the GNU General Public License version 2 or later.

See the included license files for complete licensing information.

---

## Author

**Kostas Stathopoulos — DevArt**

Website: https://devart.gr
