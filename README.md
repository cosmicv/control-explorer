# Control Explorer

A browser-based dashboard for visualizing and navigating security control frameworks — built for vCISOs managing multi-framework environments.

## Features

- **Load any SCF-structured Excel workbook** — drag & drop or browse, processed entirely in-browser (nothing leaves your machine)
- **Filter controls** by SCF Domain, NIST CSF Function, keyword search, and minimum control weight
- **Per-column filters** — click ▼ on any column header to filter by specific values, including blanks
- **Sort** any column ascending/descending
- **Column visibility** — show/hide any core column
- **Framework selection** — toggle individual framework columns on/off
- **Detail panel** — click any row to see full control details and all framework mappings
- **Export to Excel** — exports the current filtered/sorted view with only visible columns and active frameworks

## Usage

1. Open `control_explorer.html` in any modern browser
2. Drag your SCF workbook (`.xlsx`) onto the drop zone, or click Browse
3. Use the sidebar to filter, and column headers to sort/filter
4. Click **⬇ Export to Excel** to save the current view

## Expected File Format

The workbook should follow SCF structure:

| Col | Field |
|-----|-------|
| A | SCF Domain |
| B | SCF Control |
| C | SCF # |
| D | Control Description |
| E | Conformity Validation Cadence |
| F | Evidence Request List (ERL) # |
| G | Control Question |
| H | Relative Control Weighting |
| I | NIST CSF Function Grouping |
| J+ | Framework mapping columns (auto-detected) |

Row 1 is treated as the header row. All columns beyond I are treated as framework mappings and can be toggled on/off independently.

## No Dependencies to Install

Uses [SheetJS](https://sheetjs.com/) loaded from CDN. Just open the HTML file — no server, no build step, no install.
