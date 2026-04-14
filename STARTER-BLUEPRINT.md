# COMP 3512 Assignment 2 Starter Blueprint

## 1) What to build (scope lock)
Build only what is required:
- Single-page app (one HTML page only)
- Four views:
  - Home
  - Browse
  - Single Product
  - Shopping Cart
- One popup/dialog:
  - About Us
- Shared header and footer on all views
- Data source: use compact JSON data file
- No third-party JavaScript libraries
- No extra features beyond assignment requirements

## 2) Recommended files to create
Keep it simple:
- index.html
- styles.css
- app.js

Do not create additional pages.

## 3) Build order (best for this assignment)
Use this order to reduce rework:
1. Base layout + view containers + nav wiring
2. Single Product view rendering
3. Shopping Cart logic and rendering
4. Browse filtering/sorting/searching logic
5. Home content + About popup
6. Polish styles and final testing

## 4) Core app architecture (plain JavaScript)
Use one global state object:
- products: array from JSON
- currentView: "home" | "browse" | "single" | "cart"
- selectedProductId: number or null
- cart: array of cart line objects
- browseFilters: search text, category, min/max price, sort value

Keep each behavior in a function:
- initApp()
- parseProductsFromScriptTag()
- showView(viewName)
- renderHome()
- renderBrowse()
- renderSingleProduct(productId)
- renderCart()
- openAboutDialog()
- closeAboutDialog()
- addToCart(productId)
- updateCartQty(productId, newQty)
- removeFromCart(productId)
- calculateCartTotals()
- applyBrowseFilters(products, filters)

## 5) HTML skeleton plan
Inside index.html:
- Header:
  - App title/logo
  - Nav buttons/links: Home, Browse, Cart, About
- Main:
  - section for Home view
  - section for Browse view
  - section for Single Product view
  - section for Cart view
- Footer
- About popup container (hidden initially)
- One script tag containing compact JSON text OR one approach you learned and can cite
- Script include for app.js

Important:
- Give each view section a unique id
- Start with Home visible and others hidden

## 6) Browse view requirement blueprint
Create UI controls first, then logic:
- Search input
- Category select
- Price range controls (as required by your assignment screenshot)
- Sort select
- Results area (cards/list)

Behavior flow:
1. Start from full products array
2. Apply search filter
3. Apply category filter
4. Apply price filter
5. Apply sorting
6. Render resulting product list

Each product card should include:
- Image
- Name/title
- Price
- Category (if required)
- Button/link to open Single Product view
- Add to Cart button (if required)

## 7) Single Product view blueprint
Must render from selected product id:
- Product image
- Product name/title
- Product description/details
- Product price
- Any required metadata from JSON
- Quantity input (if required)
- Add to Cart button
- Back to Browse button

## 8) Shopping Cart view blueprint
Show cart state clearly:
- One row/card per cart item
- Item name
- Unit price
- Quantity control
- Line total
- Remove button
- Subtotal
- Tax/total only if assignment requires it

Rules:
- Empty cart message when no items
- Quantity updates should re-render totals immediately

## 9) Navigation and view swapping
Use a single helper:
- hide all view sections
- show only selected section
- update currentView in state

Do not load another HTML file.

## 10) Data handling strategy (safe and simple)
Option A (lecture-friendly):
- Put JSON text in a script tag of type application/json
- Read text content
- JSON.parse into products array

Option B (advanced):
- fetch JSON file
- If you use this approach, cite resources because it may be beyond covered content

## 11) Visual design plan (15%)
Pick one CSS framework OR your own CSS, but do not add JS dependency from framework.
Checklist:
- Consistent spacing system
- Strong typography hierarchy
- Clear button styles (normal, hover, active)
- Card styles with clean alignment
- Responsive layout for mobile and desktop
- Visual emphasis on key actions (view details, add to cart)

## 12) Programming design + documentation plan (10%)
To score here:
- Use clear function names
- Keep functions focused (single responsibility)
- Avoid duplicate logic
- Add short comments only where needed
- Keep variable names meaningful
- Add citation comments for any external JS snippet you used

## 13) Functional test checklist (75%)
Run this checklist before submission:
- App opens to Home view first
- Header/footer always visible
- Nav swaps views without page reload
- Browse filters work correctly in combination
- Sort order changes correctly
- Clicking product opens correct single product details
- Add to cart works from all required entry points
- Cart quantity updates and totals update correctly
- Remove item works
- Empty cart state displays correctly
- About popup opens and closes correctly
- No console errors

## 14) 2-day schedule from now
Day 1:
- Build HTML containers + nav + show/hide system
- Parse product data
- Complete Single Product + Cart logic

Day 2:
- Complete Browse filters/sort/search
- Style all views
- Full test checklist + bug fixes
- Final cleanup and submission packaging

## 15) Final submission checklist
- Single HTML page named exactly as required
- Only required files included
- JSON source is the compact version
- No forbidden JS libraries
- No extra features added
- Manual test checklist completed
- Code comments include citations for any external snippet used

---

If you want, next step can be a starter scaffold where I generate the initial index.html, styles.css, and app.js with only the required containers and no extra features.