# Billing Studio - test-billing-soft

Browser-local service billing app with violet/glass dark and light themes, dense spreadsheet tables and linked records. The public website is hosted using GitHub Pages from this repository.

## Run

Open the GitHub Pages website, or download `index.html` and serve it locally with `python -m http.server`. The built HTML includes its CSS and JavaScript and does not load remote scripts, fonts or APIs.

Editable source is in `1-test-billing-soft-v6-source.zip`. Extract it, then run:

```
npm ci
npm run dev
npm run build
npm test
```

The source uses React and TypeScript; the deployed output is static HTML, CSS and JavaScript.

## What works

- Customers, invoices, estimates, GST/discount calculations and partial payments.
- AMC contracts and service visits, daily jobs, stock movements, technician commission and cash handovers.
- Period reports, Excel-compatible CSV, browser Print/Save PDF, JSON backup/restore and deleted-record recovery.
- Dense column-and-row tables. Phones use the section picker and a per-row Details control. Wide viewports, including Chrome Desktop site on phones, show the sidebar by default. The Phone layout button can force the compact app layout.
- Dark/light themes and browser-local state. Only fictional demo records are shipped.

For normal phone sizing, turn Chrome's Desktop site setting off. That setting can zoom out the entire website independently of the app's layout.

## Limits

This is a functional preview, not production accounting software. Data stays in this browser and origin, not GitHub or a shared server. It does not sync between devices. Data from another hosting origin is not transferred automatically: download a JSON backup there, then restore it here if needed.

Keep backups. Browser storage can be cleared or fail. The preview has a small data-size limit (about 15 KB). JSON backups are not encrypted. There is no authentication, multi-user database, SMTP sending, real payment processing, XLSX export, or security guarantee. PDF output uses the browser print dialog.

The earlier `source-initial.zip` is an archive of the first version, not the current source.
