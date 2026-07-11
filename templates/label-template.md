# Shipment Label Template

## Overview

The shipment label is generated automatically after a Production Order reaches the required quantity.

Each scanned piece produces one label, allowing complete traceability throughout the expedition process.

---

## Data Source

Table:

`LANÇAMENTOS`

The template iterates through every scan associated with the completed Production Order.

---

## Iteration

The labels are generated using the following AppSheet template expression:

```appsheet
<<Start: ORDERBY(
    FILTER(
        "LANÇAMENTOS",
        [OB_ID] = [_THISROW].[OB_ID]
    ),
    [DATA/HORA]
)>>
```

This guarantees that labels are printed following the scan sequence.

---

## Printed Fields

Each label contains:

- Production Order
- Material Code
- Material Description
- Color Code
- Color Description
- Total Weight
- Barcode
- Scan Date and Time

---

## Barcode

The barcode image is dynamically generated using the value stored in the `BARCODE` column.

---

## End of Iteration

```appsheet
<<End>>
```

The iteration finishes after processing every scan belonging to the selected Production Order.

---

## Output

One PDF document containing one label for each scanned piece.

---

## Dependencies

- LANÇAMENTOS
- BASE PCP
- Barcode Generation Formula
- Generate PDF Bot

---

## Business Value

Using an automated template guarantees standardized shipment labels, eliminates manual document preparation and improves traceability during the expedition process.
