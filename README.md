# Control Explorer

A browser-based dashboard for visualizing and navigating security control frameworks — built for vCISOs managing multi-framework environments.

## Features

- **Load any SCF-structured Excel workbook** — drag & drop or browse, processed entirely in-browser (nothing leaves your machine)
- **Filter controls** by SCF Domain, NIST CSF Function, keyword search, and minimum control weight
- **Per-column filters** — click ▼ on any column header to filter by specific values, including blanks
- **Sort** any column ascending/descending
- **Column visibility** — show/hide the nine detected SCF core fields (domain, control, SCF #, description, cadence, ERL, question, weight, NIST CSF)
- **Framework selection** — toggle any *other* column on/off (framework mappings plus SCF extras such as Possible Solutions or PPTDF, in spreadsheet order)
- **Detail panel** — click any row to see full control details and values for every non-core column
- **Export to Excel** — exports the current filtered/sorted view with only visible columns and active frameworks

## Usage

1. Open `control_explorer.html` in any modern browser
2. Drag your SCF workbook (`.xlsx`) onto the drop zone, or click Browse
3. Use the sidebar to filter, and column headers to sort/filter
4. Click **⬇ Export to Excel** to save the current view

## Getting the SCF Workbook

This tool is designed to work with the **Secure Controls Framework (SCF)** master workbook, which is available as a free download from the SCF team:

**[Download the SCF workbook →](https://securecontrolsframework.com/free-scf-content/scf-download/)**

The workbook includes the full SCF control library pre-mapped to dozens of frameworks (NIST 800-53, CIS Controls, CMMC, ISO 27001, SOC 2, and many more). Download the `.xlsx` version and load it directly into Control Explorer.

The SCF workbook contains multiple sheets. When you load it, Control Explorer will display a sheet picker listing all available sheets — the **SCF 2025.4** sheet will be highlighted as recommended. Single-sheet workbooks load directly without prompting.

## Expected File Format

Row 1 is the header row. **Core columns** are found by matching header text (not fixed Excel positions), using names the SCF workbook typically uses:

| Typical field | Header cues (examples) |
|---------------|-------------------------|
| SCF Domain | contains `SCF Domain` |
| SCF Control | `SCF Control` (exact preferred) |
| SCF # | contains `SCF #` |
| Control Description | contains `Control Description` |
| Cadence | `Conformity Validation` / `Validation Cadence` |
| ERL # | `Evidence Request List` / `ERL #` |
| Control Question | contains `Control Question` |
| Weight | `Relative Control Weighting` / `Control Weighting` |
| NIST CSF | `NIST CSF Function` / `NIST CSF 2.0` / `NIST CSF` |

**Everything else** (any column whose index is not one of those nine detected fields) appears under **Frameworks** in the sidebar—whether it is a formal framework mapping (NIST 800-53, ISO 27001, …) or an extra SCF column (e.g. Possible Solutions, PPTDF). Each can be toggled on or off independently. Columns are ordered left-to-right as in the workbook.

The classic SCF layout places the nine core fields in columns A–I and framework mappings from column J onward, but the app does not rely on fixed letters if your sheet order differs.

## No Dependencies to Install

Uses [SheetJS](https://sheetjs.com/) loaded from CDN. Just open the HTML file — no server, no build step, no install.
