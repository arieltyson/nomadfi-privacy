---
title: NomadFi Privacy Policy
---

# NomadFi Privacy Policy

**Last updated:** November 10, 2026

NomadFi is a privacy-first financial decision app for people whose financial lives span more than one country. The app is designed to help users choose the right card, reduce avoidable fees, manage credit timing, and organize supporting financial context without turning their financial history into an ad-tech profile.

NomadFi is built around a simple rule: **your financial data stays on your device unless you explicitly export or share something yourself, or turn on Bank Connections.** Bank Connections is optional. It is the only feature that stores financial records on a server, and it is described in full below.

## Summary

- **No account sign-up required** for the app itself; Bank Connections uses Sign in with Apple
- **No analytics**
- **No advertising SDKs**
- **No third-party tracking**
- **No server-side storage of your financial records unless you turn on Bank Connections**, which stores bank balances and transactions in Canada so they stay current while your iPhone is closed
- **Ask FiBot answers on your device** with Apple Intelligence; your questions and its answers are never sent to NomadFi
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
| **Notification preferences and pending reminder state** | Lets the app schedule local reminders you opt into | On-device only | Until you change settings, the reminder fires, or you delete all app data |

## Bank Connections (optional)

Bank Connections links your bank accounts through [Plaid](https://plaid.com) so NomadFi stays up to date without you importing anything. It is off until you turn it on in **Settings › Financial Connections › Bank Connections**, agree to server storage, and sign in with Apple.

### How it works

1. **You sign in with Apple.** NomadFi asks Apple for no name and no email address. Apple gives NomadFi a random identifier that is unique to NomadFi; NomadFi uses it only to tell your data apart from anyone else's.
2. **You sign in to your bank through Plaid.** Your bank username, password and security answers go to Plaid and your bank, never to NomadFi. Plaid's handling of your data is described in the [Plaid End User Privacy Policy](https://plaid.com/legal/#end-user-privacy-policy).
3. **NomadFi's server keeps your bank data current.** When your bank reports new activity, Plaid notifies NomadFi's server, which fetches the changes. Your iPhone downloads them the next time you open NomadFi.

### What NomadFi's server stores

| Data | Purpose |
|---|---|
| **The random Apple identifier** and hashes of your NomadFi session keys | Recognising you and keeping others out |
| **Plaid access tokens** for each bank you connect, encrypted with Google Cloud Key Management | Fetching updates from your bank through Plaid |
| **Bank connection details**: bank name, connection status and when data was last fetched | Showing each bank's status and keeping it updated |
| **Accounts**: name, type, currency, current and available balance, and credit limit (no account or card numbers) | Your dashboard, net worth and decisions |
| **Transactions**: date and authorized date, amount, currency, description, merchant, category and whether they are pending (no locations) | Your ledger, spending summaries and decisions |
| **Delivery records** of which updates your iPhone has saved | Sending each change once, and none twice |
| **If you turn on FiBot monitoring**: the financial plan you confirm and the alerts it produces | Checking your plan against new bank activity |

The server does **not** store your bank credentials, receipts, tax documents, notes, decision drafts, FiBot conversations, location or anything you keep only on your device.

### Where it is stored and who processes it

- **NomadFi's server** runs on **Google Cloud** in Montréal, Canada (Cloud Run, Secret Manager, Cloud Key Management and Cloud Scheduler).
- **The database** is a PostgreSQL database run by **Supabase** on Amazon Web Services in Montréal, Canada (region `ca-central-1`). It is reachable only by NomadFi's server over encrypted connections; it is not exposed to the internet through any public data API.
- **Plaid** connects to your bank and may process data in the United States.
- **Apple** provides Sign in with Apple and tells NomadFi's server if you stop using Sign in with Apple with NomadFi.

These providers process data on NomadFi's behalf and under their own security and privacy terms. Storing data in Canada does not mean every provider processes it only in Canada.

### Logs

Google Cloud records basic request logs for NomadFi's server, including your IP address, the time and the address requested, for about 30 days. NomadFi's own logs record events such as "sync finished" and never include balances, transactions, account names or tokens. Rate limiting uses a keyed hash of IP addresses, not the addresses themselves.

### Retention and deletion

- **Disconnecting a bank** stops updates immediately, asks Plaid to revoke NomadFi's access, and deletes that bank's encrypted access token once Plaid confirms. History already on your iPhone stays there.
- **Delete All My Data** first asks NomadFi's server to delete your hosted account. The server stops all updates, revokes Plaid and Sign in with Apple access, then deletes every bank record it holds for you.
- **Signing out** of Bank Connections ends your session on that iPhone; your hosted data stays until you disconnect or delete it.
- **Backups:** NomadFi does not currently keep backups of hosted bank data, so deleted data is gone once deletion finishes. If that changes, this policy and the app will state how long backups are kept.

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

If you turn on Bank Connections, bank balances and transactions are stored on NomadFi's server as described in [Bank Connections](#bank-connections-optional).

NomadFi does **not** upload your receipts, tax documents, subscriptions, notes or decision history to a NomadFi server. Balances and transactions you enter manually, import from CSV or read through FinanceKit stay on your device.

## Ask FiBot

Ask FiBot answers questions about your finances with Apple Intelligence's on-device model. NomadFi builds a short list of facts from the data on your iPhone, the model answers from those facts, and NomadFi checks every figure in the answer against them. Your questions, the facts and the answers stay on your iPhone and are never saved: they are cleared when you start a new conversation or NomadFi closes.

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

- **No email address**; Bank Connections uses Sign in with Apple without requesting your name or email
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

Your data only leaves your device when **you** turn on Bank Connections (see above) or explicitly choose to share or export something, such as:

- exporting a report
- sharing a document through Apple's share sheet

Granting FinanceKit authorization does **not** send your financial data to a NomadFi server. It allows NomadFi to read eligible on-device Wallet financial data through Apple's framework on supported devices.

## Security Measures

NomadFi includes security features designed to reduce accidental exposure:

- app files that are unreadable while your iPhone is locked
- compatibility with iOS's own Require Face ID for apps, which you can turn on by touching and holding the NomadFi icon
- privacy blur in the app switcher when the app backgrounds
- device-only Keychain storage for sensitive app settings
- metadata stripping for stored and exported receipt images
- for Bank Connections: encrypted connections everywhere, bank access tokens encrypted with Google Cloud Key Management and readable only by NomadFi's server, sign-in limited to approved Apple accounts during the pilot, and a database that refuses access to anything but NomadFi's server

No software can guarantee absolute security, but NomadFi is intentionally designed to minimize how much sensitive data can leave your device in the first place.

## Data Deletion

You can permanently remove your data from inside the app:

- Open **Settings**
- Go to **Privacy & Security**
- Choose **Delete All My Data**

That flow is designed to remove app records, receipt images, Keychain items used by the app, local notification state, and other locally stored NomadFi data. If you use Bank Connections, it first asks NomadFi's server to delete your hosted data as described in [Retention and deletion](#retention-and-deletion), and keeps your local data if that request can't be confirmed, so you can try again.

## Children's Privacy

NomadFi is not directed to children under 13, and we do not knowingly build features to collect personal data from children.

## Changes to This Policy

If NomadFi's privacy model changes materially, this page will be updated and the date at the top will change.

## Contact

If you have questions about this privacy policy, contact:

**[arieltyson30190@gmail.com](mailto:arieltyson30190@gmail.com?subject=NomadFi%20Privacy)**
