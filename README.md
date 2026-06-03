<p align="center">
  <img src="icon-512.png" alt="DebtPal Logo" width="96" height="96">
</p>

<h1 align="center">DebtPal</h1>

<p align="center">
  A local-first PWA for shared debt tracking and settlement calculation.
</p>

<p align="center">
  <a href="https://rezadadbin.github.io/debtpal_pwa/">Open the App</a>
</p>

## Overview

DebtPal is a lightweight Progressive Web App for managing shared expenses, debts, and settlements. It helps record who paid for each expense, who was involved, and how the final balance should be settled.

The app is designed for informal shared expenses such as trips, family costs, shared housing, and small group payments.

This version focuses on immediate usability: it is installable, works offline after the first successful load, and can be used without account setup or backend deployment.

## Features

* Create multiple accounting groups
* Add debt items with amount, date, payers, involved people, and notes
* Support unequal share weights for involved people
* Calculate final balances automatically
* Generate a settlement plan showing who should pay whom
* Show short calculation notes for unequal-share debts
* Visualize balances with a simple chart
* Export/import full backups or individual accountings
* Installable as a Progressive Web App
* Offline-capable after the first successful load
* Local device storage only

## Weighted Shares

DebtPal supports both equal and unequal expense sharing.

By default, every involved person has a share value of `1`. For unequal sharing, each person can be assigned a custom share weight.

Example:

* Expense: `700`
* Family A: `4` shares
* Family B: `3` shares
* Total shares: `7`
* One share: `700 / 7 = 100`
* Family A owes `400`
* Family B owes `300`

This makes the app useful when equal splitting is not accurate.

## Settlement Logic

For each debt item, DebtPal:

1. Divides the total amount by the sum of all involved shares.
2. Calculates how much each involved person owes.
3. Credits each payer by the amount they paid.
4. Computes final balances across all debt items.
5. Generates a simplified payment plan between debtors and creditors.

## Development Approach

DebtPal is currently implemented as a static local-first PWA. This choice was made to make the first usable version available quickly, with minimal setup and no dependency on a running server.

Instead of requiring user accounts, backend deployment, or database configuration, the app stores data locally in the browser and supports JSON import/export for backup and transfer.

This keeps the initial version simple and immediately usable on mobile devices. A backend-based version would be more appropriate for future versions with collaboration, cloud sync, authentication, and automatic backup.

## Technology

HTML, CSS, Vanilla JavaScript, localStorage, Service Worker, and PWA manifest.

## Future Improvements

Possible future improvements include:

* optional cloud synchronization
* user accounts and authentication
* automatic backup
* multi-device support
* multi-user shared accountings
* currency labels
* recurring expense templates
* improved charts and reports
* backend/database integration

## Scope

DebtPal is not a banking system or a full accounting platform. It is a focused utility for informal shared-debt tracking and settlement calculation.

## License

No license has been selected yet.
