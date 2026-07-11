# Slice: OB_Do_Dia

## Overview

The `OB_Do_Dia` Slice filters the Production Orders to display only the most recent expedition batch.

Instead of exposing every historical Production Order, the application automatically limits the user interface to the latest available shipment date.

---

## Purpose

The Slice simplifies the operator workflow by displaying only the Production Orders scheduled for the current expedition.

This reduces navigation complexity and minimizes the risk of selecting outdated Production Orders.

---

## AppSheet Expression

```appsheet
[DATA ENVIO] =
MAX(
    BASE PCP[DATA ENVIO]
)
```

---

## How It Works

1. Retrieves every value from the `DATA ENVIO` column.
2. Determines the most recent date.
3. Filters the table.
4. Returns only Production Orders that belong to the latest expedition batch.

---

## Source Table

BASE PCP

---

## Used By

- Production Orders View
- Operator Navigation

---

## Business Value

Displaying only the latest Production Orders improves usability, reduces operational errors and keeps the expedition process focused on the current production schedule.
