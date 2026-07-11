# Total Weight Calculation

## Overview

The total weight of a Production Order is calculated dynamically by summing the weight of every successfully scanned piece associated with that order.

This value is implemented as a Virtual Column in the `BASE PCP` table.

---

## Purpose

The calculation provides the accumulated weight of all scanned pieces and is used during the expedition process and PDF generation.

---

## AppSheet Expression

```appsheet
SUM(
  SELECT(
    LANÇAMENTOS[PESO],
    [OB_ID] = [_THISROW].[OB]
  )
)
```

---

## How It Works

1. Retrieves every scan associated with the current Production Order.
2. Extracts the `PESO` value from each record.
3. Sums all retrieved values.
4. Returns the current total weight.

---

## Dependencies

- BASE PCP
- LANÇAMENTOS

---

## Used By

- Production Order Details
- Expedition Progress
- PDF Label Generation

---

## Business Value

Calculating the total weight dynamically guarantees that the displayed value always reflects the current expedition status without storing redundant information.
