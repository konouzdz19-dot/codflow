# Big Hadj Upstream Synchronization Tracker

> **CRITICAL FOR ALL AGENTS:**  
> Whenever checking for new upstream updates or commits from `bighadj22/codflow`, **ALWAYS check this file first**.  
> The current baseline commit recorded here represents the exact point up to which the workspace has already pulled, evaluated, and deployed updates. Only investigate and report commits that are **newer** than `LAST_SYNCED_COMMIT`.

---

## Current Synchronization State

* **Upstream Repository:** `https://github.com/bighadj22/codflow` (Git remote: `origin`)
* **Workspace Fork:** `https://github.com/konouzdz19-dot/codflow.git` (Git remote: `fork`)
* **Active Working Branch:** `main`

### Last Synced Upstream Commit (`LAST_SYNCED_COMMIT`)
* **Commit Hash:** `3340860a1f0c9e0765e79e47bc786cd470a0f52c`
* **Short Hash:** `3340860`
* **Commit Subject:** `Merge pull request #130 from bighadj22/feat/cart-legal-and-vercel`
* **Upstream Author:** Bilal Mansouri (`bighadj22`)
* **Date Synced:** September 24, 2026
* **Status:** Fully integrated, migrated (D1 0025-0030), and deployed to demo environment.

---

## Changes Incorporated Up to `3340860` (Already Handled)

The following upstream PRs and commits are **already integrated, tested, and deployed**:

1. **PR #130 (`3340860` / `16a44a7`)**: `feat: cart slide-over, checkout page, legal pages, and vercel deployment support`
   - **Slide-over Cart & Checkout Page:** Full slide-over drawer cart, multi-item checkout, free delivery threshold meter, custom delivery rates.
   - **Store Legal Pages:** Managed legal pages (Terms, Privacy, Refund, Shipping) across ar/fr/en with RichText editor in dashboard.
   - **Dual Deployment Architecture:** Added `@astrojs/vercel` adapter alongside `@astrojs/cloudflare` to address Algerian ISP (Algérie Télécom) routing/peering timeouts toward Cloudflare Anycast IPs.
   - **D1 Migrations:** `0026_store_delivery_pricing_settings`, `0027_stores_cart_enabled`, `0028_abandoned_orders_items`, `0029_landing_page_pixel_config`, `0030_store_pages`.
2. **PR #129 (`b5db8bf` / `cbb8c39`)**: `feat(abandoned): capture and manage abandoned orders` (abandoned checkout recovery tracking).
3. **PR #128 (`9515192` / `e324021`)**: `feat(products): support markdown and rich-text format for product descriptions` (`0025_product_description_format`).
4. **PR #125 (`9bc723d` / `9113994`)**: `ci: add production build steps to all CI jobs`.
5. **PR #124 (`26c88ab` / `b29e9f3`)**: `chore(deps): security bumps hono 4.13.7, astro 7.3.2, js-yaml 4.3.2 + cloudflare adapter 14.3.1`.
6. **PR #123 (`ba20d16` / `ee07f14`)**: `chore(deps): bump react and react-dom to 19.3.0 with root lockfile sync`.
7. **PR #99 (`d9c5bc9`)**: `chore(deps): bump qs from 6.15.3 to 6.16.0`.
8. **PR #119 (`ed00a0e` / `4544db9`)**: `fix(theme01): redirect straight to thank-you after order submission` (Instant PRG 303 Redirect).
9. **PR #118 (`cb60004` / `4c90916`)**: `feat(products): add show-in-store toggle with landing-page exemption`.
10. **PR #117 (`12bdc2b` / `f7a8dc6`)**: `fix(products): make delete a hard delete and surface identity conflicts as 409s`.
11. **PR #116 (`aae2e81` / `9037cca`)**: `feat(theme01): custom 404 page matching the storefront`.
12. **PR #115 (`99f1890`)**: `fix(theme01): keep footer at bottom on short pages` (Sticky footer).
13. **PR #114 (`00f18fa` / `e4cd850`)**: `feat(landing-pages): store uploaded images as WebP`.
14. **PR #113**: MCP v2 protocol overhaul and structured tool definitions.

---

## Local Demo Deployment Status

The demo environment (`CODFLOW BIGHADJ`, account `f53b2653e387a547fef4e5208b531f44`) is fully synced, migrated, and live:
* **API Server:** `https://codflow-server.codflow-bighadj.workers.dev` (v`d3b2f919`)
* **Dashboard:** `https://codflow-dashboard.codflow-bighadj.workers.dev` (v`5263be92`)
* **Storefront (theme01):** `https://codflow-os-theme01.codflow-bighadj.workers.dev` (v`0968fc39`)

---

## Standard Protocol for Checking Upstream Updates

Whenever the user asks to check Big Hadj repository for new updates:
1. Run `git fetch origin` in `c:\Users\HP\Projects\Rymes-Workspace\CODFLOW-BIG-HADJ`.
2. Inspect strictly the delta beyond the recorded baseline:
   ```powershell
   git log 9bc723d..origin/main --oneline --decorate
   ```
3. **If empty:** Report clearly that upstream has **no new commits** since the baseline `9bc723d` (PR #125).
4. **If new commits exist:**
   - Summarize only the *new* commits.
   - Explain what problems they solve.
   - Assess impact and provide recommendations.
5. Once any new commits are pulled and integrated, update `LAST_SYNCED_COMMIT` in this document.
