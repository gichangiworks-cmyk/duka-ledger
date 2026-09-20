# Duka Ledger

A simple dashboard for shop owners to record customer debts and payments.

## Shop app
Open index.html through GitHub Pages. Add a customer, record debt, and record payments as they arrive. Search customers by name or phone. Use Shop settings to copy a backup before changing devices or clearing browser data.

## Monthly approval
The supplied 21-day trial is preserved. After the trial, the dashboard is locked until the current month has a signed approval for KSh 250. Backup and renewal controls remain available. Owners may also pay during the trial.

Open admin.html. Choose your private admin key file (kept separately from this repository), enter the shop code and month, confirm the payment has been received, and copy the approval code to the shop owner. The owner pastes it in Shop settings → Enter renewal code. The fee is fixed at KSh 250. Approval covers the selected calendar month, not 30 days from payment.

The admin screen signs locally using ECDSA P-256. The public verification key ships with the site; the private signing key never belongs in this repository. Keep a private backup of the signing key. Approval history is browser-local and can be exported from the admin screen.

## Limits
This is a static browser app, not a shared cloud service. Records do not sync across devices. Payments are verified manually outside the app. There is no user account system or server-side billing enforcement. Signed codes prevent issuing valid approvals without the private key, but someone controlling their browser can alter local code, time or storage. Use a backend for tamper-resistant paid access. The original placeholder renewal WhatsApp contact is disabled until the real operator number is configured.

M-Pesa phone prompts are not live: no payment integration has been provided. The payment screen states this and disables collection. A payment backend must verify KSh 250 received before signing approval, authenticate shops, and enforce subscriptions on server-side data access to prevent client tampering.
