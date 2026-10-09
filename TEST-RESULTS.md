# First-preview verification

Executed 9-10 Oct 2026. Fake data only.

- Production Vite build passed.
- 8 business-engine assertions passed.
- 22 browser integration/layout checkpoints passed using Chrome: dashboard/light/dark, customer create/edit, reopen persistence, invoice GST/discount, overpayment rejection, partial payment, invoice preview/items CSV, empty search/reset, stock movement/negative-stock rejection, daily log stock/payment linkage, invoice balance update, cash handover limits, AMC scheduling/completion, report CSV/print preview, JSON download/restore, invalid backup rejection, delete/restore, all 11 sections at 320/390/1280px with no document overflow, dark mobile.
- Actual mobile and desktop pixels inspected. Invoice arithmetic: 2 x 500, discount 100, GST 18% = 1,062; receipt 400 = 662 due; later job receipt 200 = 462 due. Technician collection 600 minus handover 300 = 300 held. Parts 8 + receipt 2 - job use 1 = 9.
- Clipboard and OS Print dialog completion are browser/device dependent. Automated checks cover export files and the printable document, not a physical printer or external message delivery.
- Private review preview has session-only state for unauthenticated/agent preview. Owner review state is browser/account scoped. Standalone build uses localStorage; reload persistence was tested there.

This verifies the tested first-preview paths, not every possible input or production deployment. No independent security audit or desktop-parity certification.

Additional hosted-review checks: customer, invoice, partial-payment and settings save passed with keyboard Space activation, all 11 sections exercised at 320/390/1280, dark mode verified. Hosted iframe pointer automation had scroll-coordinate mismatch; standalone pointer flow passed.
