# Social Desk V2

A local-first personal CRM for social media management. No paid API, server, login or Firebase configuration required.

## Start

Unzip and open `index.html` in a recent Chrome, Edge, Firefox or Safari browser. If your browser restricts IndexedDB on file:// pages, serve this folder locally using `python -m http.server 8080` and open `http://localhost:8080` (Python is only needed for that optional local server). Keep using the same browser and origin to access your records.

## Included

- Editable client profiles and client workspaces
- Editable package templates and per-client subscription prices/deliverables
- Idempotent recurring invoice generation (once per subscription per month), partial payments, balances, payment history
- One-tap WhatsApp reminder drafts (you review and send; client phone needs country code)
- Monthly content calendar, approval/publishing workflow, deliverable progress
- AI planning/caption/design/report prompts copied to ChatGPT manually
- Monthly reports with manually entered insights, print-to-PDF through the browser
- JSON export and full restore
- Responsive desktop/mobile UI
- Editable demonstration Umrah travel client, sample invoice and 14 planned content ideas

## Important limitations

Data is only in the current browser's IndexedDB, not synced between devices. Back up regularly under Settings. Import **replaces** all local records. Clearing browser/site data may erase records. The dashboard does not publish to Instagram, send WhatsApp messages automatically, connect to payment gateways, verify payments, or call an AI model directly. There is no authentication or actual multi-user access yet. Future migration to Firebase will require server-enforced security rules and proper account permissions.

The sample client, invoice, and content are examples, not real bookings or claims. Never publish unverified travel, visa, hotel, catering, pricing, or availability details. This is not tax-compliant invoicing software by itself; consult a professional about applicable invoicing/GST requirements.

## Recurring billing rules

The first invoice uses the subscription start date, later monthly invoices use the configured billing day (capped at the last day of short months). The system generates invoices due through the current date when opened or when you click Generate Due Invoices. It avoids duplicates using subscription ID + billing period. Paused/cancelled subscriptions do not generate new invoices. Existing invoices are not retroactively edited by package or subscription changes. If you change billing terms mid-cycle, review invoices manually. Keep exports for auditability.

## Team-readiness

Records contain `orgId`, UUID-style IDs, timestamps and references, but no role enforcement. Do not treat the local version as a secure shared workspace.


## V2.1 — Smart Content Planning

In AI Studio select a client and target month, copy the fresh monthly calendar prompt into ChatGPT, and request the JSON array. Paste the response into the importer, validate and preview, then import as drafts. The importer checks date, type, package quantities, and likely duplicate titles/captions. Existing content is preserved. If warnings appear, revise the AI output and validate again.

Content → Insights lets you record per-post reach, views, saves, shares and enquiries. The next month's prompt includes up to 80 historical content records and recent monthly insights to reduce repetition and inform creative choices. It cannot guarantee originality or performance.

AI content is NOT sent automatically; the user chooses what to paste into ChatGPT. Never paste confidential client data without permission.
