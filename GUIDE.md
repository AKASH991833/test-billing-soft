# Billing Studio - test-billing-soft

A responsive browser-local AC service billing workspace with white/slate and deep emerald light mode, a dark mode, and linked business records. Built for Akash's requested web version of the desktop billing workflow.

**Status: functional first preview, not production accounting software. The website is not publicly deployed yet. Design review comes first.**

## Run

Download the source ZIP in this repository, extract it, then:

```sh
npm ci
npm run dev
npm run build
npm test
```

Or download `index.html` and open it in a modern browser. That file is a self-contained production build with no remote scripts, fonts or APIs. For dependable storage use a local HTTP server (`python -m http.server`) rather than file://. Data stays in that browser, not GitHub.

## Working features

- Dashboard with invoice-date filtering, billed/collected/due figures and active AMC count.
- Customer creation, editing, search and history across invoices, work logs and AC units.
- Sequential invoice numbers, estimates, editable line items, GST, fixed discount, partial payments and balance due. Unique invoice numbers and overpayment checks.
- Print-ready invoice preview and browser Print / Save PDF; item CSV and manual copy/share summary.
- AMC unit and serial records, start/end dates, contract value, scheduled visits and completion notes.
- Daily work entries linked to customers, technicians, stock parts and invoice payments. Posting deducts stock and updates balances together.
- Inventory records, cost/sell price, reorder levels, positive/negative movement ledger and negative-stock guards.
- Technician commission on received invoice payments, collector-tagged cash held, and cash handovers with balance checks.
- Invoice-period financial reports, team summary, Excel-compatible CSV and browser print/PDF.
- Shop identity, invoice prefix and default GST settings.
- Plain JSON backup, schema/link validation and confirmed replace-only restore.
- Deleted-items recovery for reversible records; guards prevent breaking linked ledgers.
- Device-local activity trail, empty states, search/reset, responsive mobile controls, light/dark themes.

## Important limits

- No server, accounts, access control, cloud sync, multi-user collaboration, automatic WhatsApp/email or real payment processing.
- Browser data is **not encrypted** and can be erased. Download backups. Do not use this preview as your sole business ledger.
- The private review preview has a 16 KB storage-value limit (writes stop at 15 KB). It is for small test data, not production volumes.
- CSV opens in Excel but is not `.xlsx`. PDF uses the browser's print dialog.
- Commission is separate from cash handover. Only collector-tagged payments count as technician-held cash. This is not a full payroll/month-close engine.
- Posted logs and paid invoices cannot be deleted or silently reversed. Corrections need explicit additional ledger movements. This protects balances but is not a full credit-note/refund system.
- No verified desktop feature parity, tax-compliance certification or security guarantee is claimed.
- All shipped records are fictional. No real shop phones, UPI, QR, customer records or credentials are included.

## Testing

`npm test` covers tax/discount arithmetic, payment guards, stock guards, references, restore and CSV formula-injection handling.

`browser-tests.mjs` contains the browser integration scenario. It tests customer CRUD/persistence, invoice creation, payment guards, linked daily work, stock, handover limits, AMC visits, exports, backup/restore, trash and every section at 320/390/1280px. See `TEST-RESULTS.md` for the executed result and limits.

## Deployment

A static host can serve the standalone index.html without a database or card. Public website launch is intentionally pending the owner's design verdict. Neither the separate product marketing page nor the existing service-booking website is modified by this repository.
