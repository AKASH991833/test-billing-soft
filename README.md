# Billing Studio - test-billing-soft

Browser-local service billing app with violet/glass dark and light themes, dense spreadsheet tables and linked records. The public website is hosted using GitHub Pages from this repository.

## Run

Open the GitHub Pages website, or download `index.html` and serve it locally with `python -m http.server`. The built HTML includes its CSS and JavaScript and does not load remote scripts, fonts or APIs.

Editable source is in `1-test-billing-soft-v15-source.zip`. Extract it, then run:

```
npm ci
npm run dev
npm run build
npm test
```

The source uses React and TypeScript; the deployed output is static HTML, CSS and JavaScript.

## What works

- Customers, invoices, estimates, GST/discount calculations and partial payments.
- Per-line calculation: rate × quantity, rate × measurement (feet/metres), or flat rate-only charge. Copper pipe, wire/cable, insulation tube/foam and aluminium pipe suggest per-foot measurement. PVC, gas refill/charging, installation/service/visiting charges, jet-pump/deep cleaning and repair suggest flat charges. Stand/bracket, capacitor, PCB, motor, remote, filter and unknown parts use quantity. These are suggested billing defaults, not universal rules; review or override each line. Type an item name to see matching suggestions; use arrows then Enter/Tab or tap a suggestion to fill it. Free-text items are allowed. Suggestions apply to new lines until you choose a manual basis. The form includes Hindi-English How to use guidance and examples beside each calculation mode. Existing invoices keep their original quantity-based calculation until explicitly changed. Print, CSV, totals and tax use the same formula.
- AMC: 1/2-year contracts, whole-term included service count, planned dates/times, service types, completed/overdue visits, advance and receipt history, balance and AMC CSV. End date is the last covered day. Suggested schedules must be reviewed; no automatic invites/reminders. Existing legacy contracts keep dates and visits until edited. AMC receipts are separate from invoice receipts: log money once, not in both ledgers. Contract amount is the final whole-term agreed amount; no AMC tax calculation or payment collection.
- Daily jobs, stock movements, technician commission and cash handovers.
- Period reports, Excel-compatible CSV, browser Print/Save PDF, JSON backup/restore and deleted-record recovery.
- Full-width, full-viewport-height workspace with no centered outer frame.
- Dense column-and-row tables. Phones use the section picker and a per-row Details control. Wide viewports, including Chrome Desktop site on phones, show the sidebar by default. The Phone layout button can force the compact app layout.
- Dark/light themes and browser-local state. Only fictional demo records are shipped.

For normal phone sizing, turn Chrome's Desktop site setting off. That setting can zoom out the entire website independently of the app's layout.

## Limits

This is a functional preview, not production accounting software. Data stays in this browser and origin, not GitHub or a shared server. It does not sync between devices. Data from another hosting origin is not transferred automatically: download a JSON backup there, then restore it here if needed.

Keep backups. Browser storage can be cleared or fail. The workspace has a 2 MB data-size limit. Browser storage can still fail. JSON backups are not encrypted. There is no authentication, multi-user database, SMTP sending, real payment processing, XLSX export, or security guarantee. PDF output uses the browser print dialog.

The earlier `source-initial.zip` is an archive of the first version, not the current source.

## Fictional large demo

New browsers start with 150 synthetic customers, 15 invoices between ₹15,000 and ₹20,000 and 15 varied AMC contracts. Indian names/area labels are examples; Zero-prefixed dummy phone digits and sample addresses are not real contacts. Existing browser records are preserved. To replace an old workspace, use Settings > Load 150-customer demo, download a backup, then confirm replacement.

Invoice preview/print is a white document ordered shop, customer, technician, items and totals. Optional phone/GSTIN can be set in Settings. GST/GSTIN are hidden when the invoice GST rate is zero. A4 printing uses the browser Save PDF dialog; this is a billing preview, not a certified tax-invoice system.
