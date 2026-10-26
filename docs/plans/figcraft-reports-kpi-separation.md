# Plan: Reports KPI Cell Separation — FigCraft Design (Desktop)

## Problem

On the **Reports** page of `design/desktop/apps.figcraft`, the three KPI cards —
"Revenue this week", "Orders", "Avg. order" — appear merged into one white
block. Each card only has a 1px `#EAECF2` stroke, which is too faint against
the `#F5F6FA` app background to read as separate cells.

The **Dashboard** page's four KPI cards share the same styling and the same
merged appearance.

## Fix

Apply to the Reports KPI cards (ids 453, 456, 459) and the Dashboard KPI cards
(ids 70, 73, 76, 79):

1. **Border + shadow separation** (consistent with the auth/chooser card style):
   - `stroke: #D9DDE8`, `strokeWeight: 1.5`
   - `effects: dropShadow #303F9F14, offset [0, 8], radius 24`
2. One `set_properties` batch (single undo step).

## Verification & Save

1. Screenshot Reports frame (id 425) and Dashboard frame (id 42) — each KPI
   card must read as a distinct bordered, shadowed cell.
2. `file.save` → `design/desktop/apps.figcraft`.

## Acceptance Criteria

- [x] The three Reports KPI cells ("Revenue this week", "Orders", "Avg. order") are visually separated
- [x] The four Dashboard KPI cells are visually separated the same way
- [x] Style stays consistent with the indigo theme (border + indigo shadow)
- [x] File saved to `design/desktop/apps.figcraft`
