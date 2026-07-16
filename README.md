# Freight Class Calculator

Free NMFC freight class (density) calculator for LTL shipping — single-file static web app.

**Live:** https://freight-class-density-calculator.pages.dev/

## Features

- Density (PCF) → estimated NMFC freight class, updated in real time
- Both classification scales side by side:
  - Official **FCDC Density Guidelines** (18-class table)
  - **July 2025 NMFC 13-sub density scale** (Docket 2025-1)
- Reverse calculator — pick a target class, get the required cube or weight
- Batch mode — multiple items with per-row classes plus a combined shipment class
- Full palletizing engine (ported from the Pallet Loading Optimizer): grid /
  pinwheel / mixed-block layer layouts, per-pallet height AND weight caps that
  split the load onto more pallets, carton clearance gap, any-side-up 3-axis
  rotation, column vs interlocked stacking
- Pallet presets (GMA, Euro/EPAL, drum, beverage, automotive, half, custom) with
  overhang warnings; floor-loading mode; mixed-SKU shared pallets in batch mode
- Vehicle recommendation: auto-picks the smallest truck (26 ft box → 28 ft pup →
  48 ft van → 53 ft van) that fits the whole load within its payload
- Truck loading preview with the real per-carton layout drawn on each pallet
  (isometric SVG, no 3D library); 40 ft / 20 ft containers for export planning
- `in + lbs ↔ cm + kg` one-click unit conversion
- Shareable result links, printable PDF report, local calculation history
- Free embeddable widget (`?embed=1`)
- English / Korean UI

## Architecture

One self-contained `index.html` — no build step, no dependencies, no server.
Deploy anywhere static files are served (built for Cloudflare Pages).

## Disclaimer

Estimates are density-based only. Actual classification depends on stowability,
handling and liability per the official NMFC. Not affiliated with NMFTA.
