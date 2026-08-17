# DevArt Polls for Joomla

Polls and surveys for Joomla 6, designed for production websites that need anonymous voting, Joomla article-backed answers, cache-safe frontend rendering, and simple survey response handling.

![Joomla](https://img.shields.io/badge/Joomla-6.x-blue)
![PHP](https://img.shields.io/badge/PHP-8.3%2B-green)
![Release](https://img.shields.io/badge/Version-1.2.2-orange)
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

## Version 1.2.2

DevArt Polls 1.2.2 is the current stable release. It adds frontend translations
for French, German, Spanish, Italian, and Brazilian Portuguese while retaining
the Joomla article-backed answers and refined Questions interface from 1.2.1.

The release has completed Joomla installation and frontend QA.

### Highlights

- Poll and Survey modes
- English, French, German, Spanish, Italian, and Brazilian Portuguese frontend languages
- Joomla article-backed poll and survey answers
- Fast bounded article picker that avoids full content counts
- Editable answer titles and 300-character plain-text introductions
- Article intro image support with full article image fallback
- Drag-and-drop and accessible up/down answer ordering
- Numbered answer cards with compact image previews
- Same-window or new-window article title links
- Optional verified email voting with a short-lived 6-digit code
- One vote per verified email address for each poll or survey
- Privacy-focused voter identity hashing without plaintext email storage
- Cache-safe voting with client hydration via `vote.refresh`
- Duplicate protection with database unique constraint
- Cloudflare-aware client IP handling (IPv4 and IPv6)
- Optional Proof of Work, reCAPTCHA v2, and Cloudflare Turnstile
- Survey response manager with CSV export
- JSON import/export for poll and survey definitions
- Administrator dashboard with stats and recent items
- GitHub-based Joomla update server support

---

## Package Contents

The installable package includes:

- `com_devartpolls` — Polls and surveys component
- `mod_devartpoll` — Frontend poll/survey module

Install or update using the full package only:

`pkg_devartpolls_v1.2.2.zip`

---

## Frontend Languages

The component site output and frontend module include:

- English (`en-GB`)
- French (`fr-FR`)
- German (`de-DE`)
- Spanish (`es-ES`)
- Italian (`it-IT`)
- Brazilian Portuguese (`pt-BR`)

The five non-English translations were generated automatically and require
review by native speakers. Corrections and improvements are welcome through
GitHub. The administrator interface remains in English.

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

- Page HTML can be cached by Joomla or Cloudflare Full Page Cache
- Vote endpoints send `Cache-Control: no-store`
- After page load, the module hydrates visitor state and live counters through `vote.refresh`
- Stale “already voted” markup is corrected for the current visitor

This keeps voting independent of full-page cache.

---

## Duplicate Protection

Available modes:

- None (testing only)
- Cookie only
- Cookie + IP hash
- Cookie + IP hash + User-Agent hash
- Verified email code

When duplicate protection is enabled, the database enforces `UNIQUE (poll_id, visitor_hash)`.

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

The code expires after 10 minutes, can be used only once, and allows a maximum
of five verification attempts. Resend cooldowns and per-email and per-IP request
limits help prevent automated abuse and excessive email delivery.

Verified email voting enforces **one verified email address = one vote per poll
or survey**. It does not guarantee one physical person per vote because visitors
may have access to multiple or disposable email addresses.

---

## Bot Protection

Optional bot protection modes:

- Disabled
- Joomla Proof of Work
- reCAPTCHA v2
- Cloudflare Turnstile

Bot protection is independent from duplicate protection.

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

   `pkg_devartpolls_v1.2.2.zip`

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

Version 1.2.2 is a safe update from the verified `1.2.1` release. Existing
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

`pkg_devartpolls_v1.2.2.zip`

GitHub releases:

https://github.com/devartgr/joomla-devart-polls/releases

Direct download:

https://github.com/devartgr/joomla-devart-polls/releases/download/1.2.2/pkg_devartpolls_v1.2.2.zip

SHA-256:

`59ae2bd135af7751c5b14ffdace1de42133be6ebafa4feb9abc176d2744c54f0`

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
