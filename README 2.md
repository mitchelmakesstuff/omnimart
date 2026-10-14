# OmniMart

A marketplace app for Nigeria where people sell anything, pay by bank transfer held in escrow, and get items delivered by verified dispatch riders.

**Live preview:** https://mitchelmakesstuff.github.io/omnimart/

This repository is a finished, working front-end prototype. Every screen and flow runs in the browser, but it has no server: data is saved on the visitor's own device and no real money moves. The launch specification (a separate document) describes exactly what a production build needs.

## What it does

- **Buying and selling.** Browse by category and city, search, save listings, follow sellers, chat, make offers, list items with photos.
- **Escrow.** The buyer pays by bank transfer and the money is held. The buyer has 48 hours after delivery (7 days after paying if they collect it themselves) to confirm or report a problem. If they do neither, the payment is released to the seller automatically. A reported problem freezes the money until the owner decides.
- **Dispatch riders.** Application with an eligibility checklist, owner approval, an online/offline switch, one job at a time, a pickup photo, and a delivery code the buyer gives the rider.
- **Trust badges.** Sellers, buyers and riders carry a green, yellow or red badge based on their record.
- **Owner tools.** Revenue by stream (6% service fee, delivery commission, featured listings), a ledger, rider approvals and a disputes queue.
- **Automatic discounts** for new and slow-selling listings, paid-for featured listings, notifications, light and dark themes.

## What is real and what is simulated

| Real in this prototype | Simulated (needs a backend) |
| --- | --- |
| All screens, navigation and design | Accounts and sign-in |
| Fee, discount and refund maths | A shared database between users |
| Escrow rules, countdowns and automatic release | Real bank transfers and payouts |
| Dispute flow and owner decisions | Live rider dispatch (riders and jobs are demo data) |
| Photo upload (resized before saving) | Real-time chat (seller replies are scripted) |

## Try it

1. Open the live preview, or open `index.html` in any browser.
2. Tap **Sell** and list an item. You can buy your own listing to try checkout, escrow and delivery.
3. **Settings, then Owner sign-in** creates an owner PIN on your device. Once signed in, **Demo: skip ahead 24 hours** lets you watch the 24-hour warning and the automatic release happen without waiting.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | The whole app: markup, styles and logic in one file, no build step |
| `manifest.webmanifest` | Lets the app be added to a phone's Home Screen |
| `apple-touch-icon.png`, `icon-192.png`, `icon-512.png` | App icons |
| `favicon.svg`, `favicon-32.png` | Browser tab icons |

## Hosting

It is a static site. Upload the files to any static host (GitHub Pages, Netlify, Cloudflare Pages). There is nothing to install. The only outside request is the optional Google Fonts stylesheet; the app falls back to system fonts without it.

## Notes for the next developer

- All saved data lives in the browser's `localStorage` under the key `mp_state`.
- Fee rates, delivery fee, rider share, featured-listing fee and the escrow windows are constants at the top of the script, so they are easy to find and change.
- The owner PIN is only a preview gate. A real build needs server-side roles.
- No license file is included yet. Add one before sharing the code more widely.

## What comes next

A production version needs accounts, a shared database, a licensed payment provider for escrow and payouts, and live dispatch. The launch specification covers the screens, data model, business rules, payment and regulatory requirements, safety rules and a launch checklist.
