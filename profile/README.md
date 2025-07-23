# 📊 Instagram Analytics

> **Status:** 🚧 Initial web‐service approach scrapped.  
> 🎯 Next up: Chrome-extension-based implementation in a fresh repo.

**Working Repository**: [vxnquish/Unfollowers](https://github.com/vxnquish/Unfollowers)


---

## Background

We initially set out to build a standalone web service that would allow users to:

1. Log in with their Instagram account (or submit their username).
2. View ◆ Who follows me ◆ Who I follow ◆ Who doesn’t follow me back ◆ Top likers.

This service was supposed to fetch data directly from Instagram’s APIs and present it in a clean dashboard.

---

## What Went Wrong

1. **Official Instagram APIs**  
   - Instagram’s Graph API requires an approved app review and only exposes limited endpoints for business or creator accounts.  
   - **Followers/following lists** and **top‐likers** data are not available to third-party web services without elevated permissions.

2. **Third-Party APIs**  
   - Undocumented endpoints exist, but most wrappers require the user’s credentials and trigger 2-factor authentication flows that are difficult to automate securely.  
   - Frequent breaking changes and IP-rate limits made these solutions brittle in production.

3. **2FA & Rate-Limiting**  
   - Instagram aggressively enforces two-factor authentication and rate limits login attempts.  
   - Any server-side scraper approach quickly runs into lockouts, CAPTCHA walls, or permanent bans.

---

## Why a Chrome Extension?

- **Leverage the Logged-In Session**  
  The user is already authenticated in Chrome → our extension can piggyback on those cookies to call Instagram’s private GraphQL endpoints directly.

- **No Extra OAuth or 2FA Hassles**  
  We avoid separate login flows and two-factor prompts by running entirely in the browser context.

- **Instant Prototyping & UX**  
  Data can be pulled live from instagram.com, and results shown immediately in a popup UI.

---

## What’s Next

1. **Archive/Scrap** this initial web-service code and configuration.  
2. **Create a new GitHub repo** for the Chrome Extension:
   - `manifest.json` (MV3)
   - Background service worker
   - Content script for grabbing `userId`
   - Popup UI for displaying followers/non-followers/top likers
3. **Iterate & Maintain**: keep an eye on Instagram’s front-end changes and update GraphQL query hashes as needed.

---
