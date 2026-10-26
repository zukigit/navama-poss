# Plan: App Chooser + CopyShop Pages — FigCraft Design (Desktop)

## Overview

New FigCraft document `design/desktop/apps.figcraft` with an app-chooser ("launcher") page and the 8 basic CopyShop pages, in the same 1440×900 + indigo style as the auth design (`figcraft-auth-design.md`). All pages are starter skeletons — to be edited/extended later.

## Requirements

1. **Choose app page**: user picks which app to use — CopyShop, TrainingSchool, and more (placeholder "coming soon" cards)
2. **CopyShop basics**: every basic page needed for CopyShop (Dashboard, POS, Orders, Services, Customers, Inventory, Reports, Settings)
3. Same desktop format and indigo theme as the auth pages (1440×900, Inter, indigo palette)

## Indigo Theme Tokens (same as auth design)

| Token | Hex |
|---|---|
| Primary | `#3F51B5` (Indigo 500) |
| Primary Dark | `#303F9F` (Indigo 700) |
| Primary Light | `#C5CAE9` (Indigo 100) |
| Surface / Background | `#FFFFFF` |
| App Background | `#F5F6FA` |
| Text Primary | `#212121` |
| Text Secondary | `#757575` |
| Muted / Disabled | `#9E9E9E` |
| Focus / Border | `#9FA8DA` (Indigo 200) |

Typography: Inter — headings 24/32, body 14/20, labels 12/16.
Buttons: Indigo 500 fill, white text, corner radius 8, height 44.
Inputs: 1px Indigo 200 border, height 44, corner radius 8, padding 16.

## File / Page Structure

Save file: `design/desktop/apps.figcraft` (new file; auth stays separate)

Pages in the document:

- `Choose App`
- CopyShop app pages: `Dashboard`, `New Sale (POS)`, `Orders`, `Services / Products`, `Customers`, `Inventory`, `Reports`, `Settings`

## 1. Choose App page

- 1440×900, `#F5F6FA` background
- Heading "Choose an app" (24 bold, `#212121`) + subtitle "Pick an app to get started" (14, `#757575`)
- Grid of **5 app cards** (~280×220, white fill, corner radius 16, indigo drop shadow, vertical auto layout, centered):
  - Icon circle (56px, Indigo 100 fill, simple vector glyph), app name (16 Medium), one-line description (12, `#757575`)
  - **CopyShop** — "Print & copy services" (active)
  - **TrainingSchool** — "Courses & enrollments" (active)
  - **Café** — placeholder, "Coming soon" badge chip
  - **Repair Shop** — placeholder, "Coming soon" badge chip
  - **Laundry** — placeholder, "Coming soon" badge chip
- Active cards: Indigo 500 border ("Open" affordance); placeholders: muted icon, gray badge, no border
- Card names are plain text layers — trivial to rename later

## 2. CopyShop app shell (shared by all 8 pages)

Every CopyShop page is a 1440×900 frame with:

- **Top bar** (height 64, white): "CopyShop" logo text (16 Bold, `#303F9F`), centered search input placeholder (rounded, Indigo 200 border), user avatar circle (32px, Indigo 100, initials)
- **Left sidebar** (width 240, white): nav items (44px rows) — Dashboard, New Sale, Orders, Services, Customers, Inventory, Reports, Settings
  - Current page's item highlighted: Indigo 500 fill, white text, radius 8; others: `#212121` text on white
- **Content area**: `#F5F6FA`, padding 32, page heading (24 Bold) + content below

## 3. Page contents (basic skeletons)

### Dashboard
- 4 KPI cards (white, radius 16, shadow): Today's sales, Orders today, Pending jobs, Low stock items (value 24 Bold Indigo 700, label 12 `#757575`)
- "Recent orders" mini table (Order #, Customer, Service, Status) with 4–5 sample rows
- Quick actions row: "New sale" primary button, "Add customer" secondary button

### New Sale (POS)
- Left (main): service tiles grid (2×3): B/W A4, Color A4, Binding, Lamination, Scan, Photo print — tile = icon/name/price
- Right panel (width ~360, white, radius 16): cart line items (name, qty stepper, price), divider, Subtotal / Total rows, "Charge" primary button (full width)

### Orders
- Filter chips row: All (active, Indigo 500), Pending, Printing, Ready, Done
- Table: Order #, Customer, Service, Qty, Status (colored chips: Pending amber, Printing blue, Ready indigo, Done green), Created

### Services / Products
- Header + "Add service" primary button (top right)
- Table: Name, Category, Unit price, Stock

### Customers
- Header + "Add customer" primary button (top right)
- Table: Name, Phone, Orders, Total spent

### Inventory
- Header + "Add item" primary button
- Supplies table: Item, Quantity, Unit, Low-stock level, Status chip (OK green / Low red)

### Reports
- KPI row (Revenue, Orders, Avg. order)
- Simple bar chart: 7 indigo rectangles of varying height (Mon–Sun labels) on a card
- "Top services" list card (service name + revenue)

### Settings
- Left section nav (Store, Staff, Printers, Billing — Store active)
- Basic store form card: Store name, Address, Phone input fields + "Save changes" primary button

## Execution Steps (via FigCraft MCP)

1. `file.new` (name "apps") → rename default page "Choose App" → `page.add` × 8 for CopyShop pages
2. **Gotcha:** `page.add` switches the current page — always `page.select` explicitly before building on a page (this misplaced the Login frame last time)
3. Build each page as one batch: desktop frame → shell (top bar + sidebar with the correct active item) → page content
4. Screenshot-verify each page after building; fix spacing/alignment issues
5. `file.save` → `design/desktop/apps.figcraft`

## Acceptance Criteria

- [ ] Chooser page shows CopyShop + TrainingSchool active cards and 3 "coming soon" placeholders
- [ ] All 8 CopyShop pages exist with the shared shell (top bar + sidebar)
- [ ] Sidebar highlights the current page on each screen
- [ ] Each page has its basic content skeleton (tables, cards, buttons, forms)
- [ ] Indigo theme + 1440×900 consistent with the auth design
- [ ] Saved to `design/desktop/apps.figcraft`
