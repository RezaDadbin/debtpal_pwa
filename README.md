<p align="center">
  <img src="icon-512.png" alt="DebtPal Logo" width="96" height="96">
</p>

<h1 align="center">DebtPal</h1>

<p align="center">
  A local-first Progressive Web App for tracking shared debts and calculating settlements.
</p>

<p align="center">
  <a href="https://rezadadbin.github.io/debtpal_pwa/">Open the App</a>
</p>

## Overview

DebtPal is a small local-first Progressive Web App for managing shared debts, informal expenses, and settlement calculations. It helps track who paid for an item, who was involved in the cost, and how the final balance should be settled between people.

The project is designed for personal use, small groups, trips, shared housing, and lightweight expense tracking where a full financial management system would be unnecessary.

## Core Idea

When several people share costs, the difficult part is not only recording the total amount, but also remembering who paid, who participated in each expense, and how much each person should finally receive or pay.

DebtPal organizes this information into accounting groups. Each accounting group can contain multiple debt items. For every debt item, the user defines the total amount, payer or payers, involved people, date, optional notes, and share weights. The app then calculates final balances and suggests a simple settlement plan.

## Live App

The app is available as a Progressive Web App at:

https://rezadadbin.github.io/debtpal_pwa/

After opening the link on a mobile browser, it can be installed on the device as a PWA. Once it is opened successfully online at least once, the app files are cached and the app can work offline.

## Features

* Create multiple accounting groups
* Add debt items with amount, date, and notes
* Add one or more payers for each debt item
* Add involved people for each debt item
* Assign custom share weights to involved people
* Calculate final balances automatically
* Generate a settlement plan showing who should pay whom
* Show short share-calculation notes for unequal-share debts
* Visualize balances with a simple chart
* Export and import full JSON backups
* Export and import individual accounting groups
* Installable as a Progressive Web App
* Works offline after the first successful load
* Stores data locally on the user’s device

## Weighted Shares

DebtPal supports both equal and unequal expense sharing.

By default, every involved person has a share value of `1`, which means the expense is divided equally. However, each person can also be assigned a custom share value from `1` to `9`.

For example, if a shared expense is `700` and two families are involved:

* Family A has `4` shares
* Family B has `3` shares
* Total shares = `7`
* One share = `700 / 7 = 100`
* Family A owes `4 × 100 = 400`
* Family B owes `3 × 100 = 300`

This makes the app useful for cases where people or families should not split an expense equally.

If all shares are equal, DebtPal keeps the interface clean and does not show an unnecessary calculation note. If shares are unequal, it shows a short explanation under the debt item.

## How Settlement Works

DebtPal uses a balance-based settlement calculation.

For each debt item:

1. The total amount is divided by the sum of all involved people’s shares.
2. Each involved person is assigned their owed amount based on their share weight.
3. Each payer is credited with the amount they paid.
4. After all debt items are processed, the app calculates each person’s final balance.
5. People with negative balances owe money.
6. People with positive balances should receive money.
7. DebtPal creates a simplified payment plan between debtors and creditors.

This allows DebtPal to handle equal shares, unequal shares, multiple payers, multiple debt items, and mixed settlement cases.

## Why a Local-First PWA?

DebtPal was built as a local-first Progressive Web App instead of a full React/backend application because the goal of the project is intentionally small and personal.

The app is designed to solve a practical everyday problem: quickly recording shared debts, tracking who paid, and calculating settlements without requiring accounts, servers, deployment complexity, or backend maintenance. For this use case, a server-side database and authentication system would add unnecessary overhead.

A PWA provides the right balance:

* it can be installed on mobile devices,
* it works offline after the first load,
* it does not require an app store,
* it does not require a server-side database,
* it keeps data on the user’s own device,
* and it can be deployed as simple static files.

This design also improves privacy for personal use. Debt and expense data are not sent to a remote server; they remain in local browser storage on the device. If needed, the user can manually export and import JSON backups.

A more complex stack, such as React with a backend service, would be reasonable for a multi-user production system with synchronization, accounts, cloud backup, and collaboration. DebtPal is not trying to be that. It is a small, focused utility built to be usable quickly with minimal infrastructure.

## Privacy and Storage

DebtPal does not use a backend server, login system, or cloud database.

All data is stored locally in the browser using localStorage. This means the data stays on the device where the app is used.

Because the app does not automatically synchronize data, users should occasionally export backups if the data is important. Backups are stored as JSON files and can be imported later.

## Import and Export

DebtPal supports two backup levels.

### Full Backup

Exports or imports the entire app data, including all accounting groups and their debt items.

### Single Accounting Backup

Exports or imports one selected accounting group. This is useful when the user wants to save, transfer, or restore a specific accounting without replacing all app data.

When importing an accounting with an existing name, the app can handle it as a replacement or as a copied accounting.

## Project Structure

* `index.html`
* `style.css`
* `manifest.json`
* `sw.js`
* `icon-192.png`
* `icon-512.png`

## Technology

* HTML
* CSS
* Vanilla JavaScript
* localStorage
* Service Worker
* Progressive Web App manifest

## Running Locally

Because this project uses separate static files and a service worker, it should be served from a local static server for proper testing. Opening `index.html` directly may display the page, but full PWA behavior and offline caching require the app to be served through HTTP or HTTPS.

For normal use, the hosted PWA link is recommended:

https://rezadadbin.github.io/debtpal_pwa/

## Deployment

The app can be hosted on any static hosting service, including GitHub Pages.

After deployment, open the app URL in a mobile browser and install it as a Progressive Web App.

On mobile:

1. Open the hosted app URL.
2. Wait for the first successful load.
3. Add or install it from the browser menu.
4. Open the installed app once.
5. The app can then work offline using the cached files.

## Limitations

DebtPal is intentionally small and focused. It is not a banking application, accounting platform, or production finance system.

Current limitations include:

* no cloud synchronization,
* no multi-user collaboration,
* no automatic cloud backup,
* no authentication system,
* and no remote database.

These limitations are intentional for the current scope. The app is meant to be a lightweight personal utility rather than a full financial product.

## Future Improvements

Possible future improvements include:

* optional cloud sync,
* backup reminders,
* editable settlement rules,
* currency labels,
* recurring expense templates,
* improved charts,
* and a multi-user version with a backend.

## License

No license has been selected yet.
