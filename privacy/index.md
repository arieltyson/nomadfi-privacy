---
title: NomadFi Privacy Policy
---

# NomadFi Privacy Policy

**Last updated:** April 23, 2026

NomadFi is a privacy-first financial decision app for people whose financial lives span more than one country. The app is designed to help users choose the right card, reduce avoidable fees, manage credit timing, and organize supporting financial context without turning their financial history into an ad-tech profile.

NomadFi is built around a simple rule: **your financial data stays on your device unless you explicitly export or share something yourself.**

## Summary

- **No account sign-up required**
- **No analytics**
- **No advertising SDKs**
- **No third-party tracking**
- **No server-side storage of your financial records**
- **Optional Apple FinanceKit access only with explicit user consent**

## Data NomadFi Stores On Your Device

| Data | Purpose | Stored Where | Retention |
|---|---|---|---|
| **Financial setup data** (jurisdictions, accounts, cards, limits, statement dates, reward terms, budgets, subscriptions) | Powers NomadFi's decision engines and financial setup flows | On-device only (SwiftData in the app sandbox) | Until you edit or delete it, or use Delete All My Data |
| **Transactions and balance snapshots** (manual, CSV-imported, or FinanceKit-backed) | Power dashboard summaries, credit timing, purchase decisions, and spending context | On-device only (SwiftData in the app sandbox) | Until you edit or delete them, or use Delete All My Data |
| **Decision drafts and decision history** | Lets you capture and revisit financial scenarios | On-device only (SwiftData in the app sandbox) | Until you edit or delete them, or use Delete All My Data |
| **Tax Vault documents and receipt metadata** | Lets you review, categorize, and organize tax-related documents | On-device only (SwiftData in the app sandbox) | Until you delete them, or use Delete All My Data |
| **Receipt images you choose to import** | Lets NomadFi run on-device OCR and show the original image in Tax Vault | On-device only (`Documents/receipts/` in the app sandbox) | Until you delete the document, or use Delete All My Data |
| **OCR text extracted from receipts** | Supports receipt review and category suggestions | On-device only | Stored only if you save the scanned result |
| **Exchange-rate cache** | Supports FX and fee-awareness features | On-device only | Refreshed over time and removable with Delete All My Data |
| **App lock settings** | Stores whether App Lock is enabled and the timeout you choose | Device-only Keychain | Until you change the setting or delete all app data |
| **Notification preferences and pending reminder state** | Lets the app schedule local reminders you opt into | On-device only | Until you change settings, the reminder fires, or you delete all app data |

## Permissions NomadFi May Request

NomadFi only requests access when a feature needs it.

### FinanceKit

If your device and Apple account support FinanceKit, NomadFi may ask for permission to read eligible Apple Wallet financial data such as balances and transactions.

Per Apple's FinanceKit documentation, this data is retrieved from the **on-device** data store and is **never seen by Apple**. NomadFi uses this data only to improve balance freshness, transaction context, and decision quality inside the app.

### Photos

If you choose to add a receipt to Tax Vault, NomadFi uses Apple's photo picker so you can select an image from your photo library. NomadFi does not get broad photo-library access beyond the items you explicitly choose.

### Location

NomadFi may request location access to detect your current country for payment and card recommendations. The app does **not** store your coordinates in its financial records, and location is not used for analytics or advertising.

### Notifications

NomadFi may request notification permission for reminders you opt into, such as subscription reminders, budget alerts, exchange-rate movements, and credit-card statement close or payment due reminders. These are scheduled locally on your device.

## What Leaves Your Device

NomadFi is designed so that almost all core data stays local.

The main exception today is exchange-rate lookup:

- NomadFi fetches exchange rates from `https://open.er-api.com/v6/latest/`
- Those requests contain currency codes only
- NomadFi does **not** send your balances, transactions, receipts, names, or account identifiers in those requests

NomadFi does **not** upload your receipts, tax documents, balances, transactions, subscriptions, or decision history to a NomadFi server.

## Receipt Images and OCR

When you import a receipt image:

- OCR runs on-device using Apple's Vision framework
- the image is stored in the app sandbox, not in a shared public folder
- privacy-sensitive EXIF metadata such as GPS coordinates, device model, and capture metadata is stripped before storage and export

If you do not save the scanned result, the imported data does not become part of your long-term tax records.

## Notifications

NomadFi uses local notifications only. It does not operate a remote push-notification service for your financial reminders.

Notification content is designed to avoid exposing sensitive financial details on the lock screen. NomadFi does not place account balances, account numbers, or full financial histories into notification text.

## What NomadFi Does Not Collect

- **No email address or account registration**
- **No advertising identifier**
- **No analytics events**
- **No cross-app tracking**
- **No contact list**
- **No browsing history**
- **No health data**
- **No sale of personal data**
- **No third-party marketing SDKs**

## Data Sharing

NomadFi does not sell, rent, or share your financial data with advertisers or data brokers.

Your data only leaves your device when **you** explicitly choose to share or export something, such as:

- exporting a report
- sharing a document through Apple's share sheet

Granting FinanceKit authorization does **not** send your financial data to a NomadFi server. It allows NomadFi to read eligible on-device Wallet financial data through Apple's framework on supported devices.

## Security Measures

NomadFi includes security features designed to reduce accidental exposure:

- optional App Lock using Face ID, Touch ID, or device passcode
- privacy blur in the app switcher when the app backgrounds
- device-only Keychain storage for sensitive app settings
- metadata stripping for stored and exported receipt images

No software can guarantee absolute security, but NomadFi is intentionally designed to minimize how much sensitive data can leave your device in the first place.

## Data Deletion

You can permanently remove your data from inside the app:

- Open **Settings**
- Go to **Privacy & Security**
- Choose **Delete All My Data**

That flow is designed to remove app records, receipt images, Keychain items used by the app, local notification state, and other locally stored NomadFi data.

## Children's Privacy

NomadFi is not directed to children under 13, and we do not knowingly build features to collect personal data from children.

## Changes to This Policy

If NomadFi's privacy model changes materially, this page will be updated and the date at the top will change.

## Contact

If you have questions about this privacy policy, contact:

**arieltyson30190@gmail.com**
