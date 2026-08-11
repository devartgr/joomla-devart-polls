# DevArt Polls for Joomla

Polls and surveys for Joomla 6, designed for production websites that need anonymous voting, cache-safe frontend rendering, and simple survey response handling.

![Joomla](https://img.shields.io/badge/Joomla-6.x-blue)
![PHP](https://img.shields.io/badge/PHP-8.3%2B-green)
![Release](https://img.shields.io/badge/Version-1.0.0-orange)
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

## Version 1.0.0

DevArt Polls 1.0.0 is the first stable public release.

### Highlights

- Poll and Survey modes
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

`pkg_devartpolls_v1.0.0.zip`

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

## Frontend Module

Publish the DevArt Poll module on any site position and select a published poll or survey.

The module supports:

- Result display modes
- Chart types and themes
- Optional answer images
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

When duplicate protection is enabled, the database enforces `UNIQUE (poll_id, visitor_hash)`.

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

   `pkg_devartpolls_v1.0.0.zip`

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

Version 1.0.0 is a safe update from `0.1.0-alpha9.2.*` packages.

---

## Download

Latest release:

`pkg_devartpolls_v1.0.0.zip`

GitHub releases:

https://github.com/devartgr/joomla-devart-polls/releases

Direct download:

https://github.com/devartgr/joomla-devart-polls/releases/download/v1.0.0/pkg_devartpolls_v1.0.0.zip

SHA-256:

`523f4d4a3c9e56c901962eec82e51a2a0723a60bbda939f1daa3f9802d23a3db`

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
