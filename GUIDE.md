# Billing Studio guide

The current app instructions, phone-layout guidance, storage limits and backup steps are in [README.md](README.md).

The current editable source is [1-test-billing-soft-v26-source.zip](1-test-billing-soft-v26-source.zip). The other ZIPs are earlier versions.

Data stays in the browser. Before changing hosting origins or clearing browser data, download a JSON backup. Restore replaces the workspace, not merges it. CSV export opens in Excel; PDF uses Print/Save PDF.

## Formatted section exports (v27)

Every section now has a primary **Export Excel** (.xlsx) button and a secondary **Export CSV** button. Excel preserves styled headers, striped tables, header sort/filter dropdowns, frozen first row, sensible widths, wrapped text/row heights, numeric INR amounts and real dates. IDs/phones stay Text. First sheet is section data; Export_info records scope/current filters and Data_dictionary explains types. Empty results retain headers and filters. This is a static browser-local export, not live sync. CSV cannot preserve visual formatting or filter controls. Open .xlsx in Excel/LibreOffice or an Excel-compatible spreadsheet app; basic phone previewers may not offer filter controls. Reports still offers the full workbook with Charts on the second sheet.
