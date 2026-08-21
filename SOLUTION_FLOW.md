# Tiaanso Global — Design, Stock, Share & Order

## The problem today

Images live in **tablet folders**. Stock lives in a **register / Excel / ERP**. Orders live in **WhatsApp / paper**.

When a customer asks *“send that floral design, and how many do you have?”* the salesperson:

1. Scrolls folders on the tablet
2. Forwards several photos
3. Checks stock somewhere else
4. Types availability by hand
5. Takes the order in another chat

That is slow, error-prone, and the photos are not bound to a design code or to live quantity.

## The idea

**One Design Card is the master record.**  
A design is no longer a folder of pictures. It is a single card that binds:

| Bound to the design | Why it matters |
| --- | --- |
| Gallery (front, drape, close-up, colorways) | Replaces folder hunting |
| Design code, fabric, category | Fast search when the customer names it |
| Color × size stock | Send availability with the photos |
| Rate / MOQ | Quote without leaving the card |
| Share pack | One tap: images + stock + rate on WhatsApp |
| Order line | Take the order from the same screen |

Stock and orders never leave the design. If the picture is right, the quantity and the order are right.

---

## Roles

| Role | Device | Job |
| --- | --- | --- |
| Studio / warehouse | Tablet | Capture photos **into** a design (not into a folder) |
| Warehouse | Tablet / desktop | Update color × size stock |
| Sales | Phone / tablet | Search → send gallery + stock → take order |
| Customer | WhatsApp / catalog link | Sees photos and availability, confirms qty |

---

## End-to-end flow

```
CAPTURE (tablet)          CATALOG              SHARE                 ORDER
─────────────────         ──────────           ─────                 ─────
Open / create design  →   Search by code,  →   Pick photos       →   Pick customer
Shoot into that card      name, fabric         Auto-attach live      Color + size + qty
Tag colorway              See stock badge      stock + rate          Reserve / deduct
                          Open Design Card     WhatsApp / link       Confirm to customer
```

### 1. Capture (replaces “folder on tablet”)

1. Sales or studio opens **Capture**.
2. They search an existing design code (e.g. `TG-2148`) or create a new one.
3. Camera shoots **into that design**, not into a gallery album.
4. Each shot is tagged: view (front / back / drape / detail) and colorway.
5. The folder is gone. The design card *is* the album.

Offline-friendly: photos queue on the tablet and sync when the network is back.

### 2. Stock bind

Each design holds a matrix, not a single number:

```
Design TG-2148  Floral Voile
────────────────────────────────
          S      M      L     XL
Sage     40     70     60     40     = 210
Ivory    20     50     40     20     = 130
Indigo   18     36     24      8     =  86
────────────────────────────────
Available                              426 pcs
```

Warehouse updates this matrix. Sales never types stock by hand.  
When an order is confirmed, quantity is **reserved** (or deducted). Over-sell is blocked unless the house allows “against order”.

### 3. Customer asks → send design + stock

This is the moment the current folder method fails. The new path:

1. Customer: *“Send the floral voile, what is in stock?”*
2. Sales searches `floral` / `TG-2148` / scans a hangtag QR.
3. Design Card opens: gallery + stock matrix + rate.
4. Sales taps **Share to customer**.
5. App builds a pack:
   - selected photos (not 40 unlabelled shots)
   - design code and name
   - live stock summary
   - rate and MOQ
6. One tap sends on **WhatsApp** (or SMS / email / copy link).

Example message the customer receives:

```
Tiaanso Global
Design TG-2148  ·  Floral Voile  ·  Cotton Voile

Sage  210 pcs   Ivory  130 pcs   Indigo  86 pcs
Ready now: 426 pcs    Rate: ₹385 / pc    MOQ: 12

Reply with color + size + qty to confirm.
```

Optional later: a **view-only catalog link** so the customer opens a mini lookbook instead of a pile of WhatsApp images.

### 4. Order taking (bound to the same card)

From the same Design Card, or from a shared reply:

1. **Create order** → pick / add customer (firm, city, WhatsApp).
2. Add line: design + color + size + qty.
3. App checks stock. If short, it warns (or allows against-order).
4. Repeat for more designs. Running total is visible.
5. Confirm. Order number is generated (e.g. `TG-ORD-1042`).
6. Stock is reserved. Customer gets a WhatsApp / PDF confirmation.
7. Dispatch later marks the order shipped and clears the reserve.

Sales never re-types the design code. The photo they just sent is the SKU they just sold.

---

## Screen map (what the demo shows)

1. **Flow** — this journey, as a walkthrough.
2. **Capture** — tablet camera into a design card.
3. **Catalog** — search, stock badges, open a design.
4. **Design Card** — gallery, stock matrix, Share, Add to order.
5. **Share sheet** — photo picker + WhatsApp preview.
6. **Order** — customer, lines, stock check, confirm.
7. **Orders** — list with status (new / reserved / confirmed).

---

## What we are *not* doing in the first cut

- Full accounting / GST invoice engine (order capture is enough to start).
- Replacing an existing ERP on day one — this layer can sit in front and push confirmed orders out later.
- Public e-commerce checkout — this is a **sales-assisted** catalog, not a webshop.

Those can plug in once the Design Card is the source of truth.

---

## Why this is smarter than folders

| Folder on tablet | Design Card |
| --- | --- |
| Photos have no SKU | Every photo belongs to a design code |
| Stock is a separate question | Stock travels with the image |
| Order is a third conversation | Order is a button on the same card |
| New staff cannot find “that floral” | Search by code, name, fabric, color |
| Customer gets 12 unsorted pictures | Customer gets a labelled pack + qty |

---

## Suggested rollout

1. **Now** — Design Card + capture + share + simple order (this demo).
2. **Next** — WhatsApp catalog link, hangtag QR, customer list, order PDF.
3. **Then** — ERP / tally push, barcode, dispatcher app, against-order production.
