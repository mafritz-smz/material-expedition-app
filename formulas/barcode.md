# Barcode Generation

## Overview

Each completed Production Order receives a unique barcode that is embedded into the generated shipment label.

The barcode is generated dynamically using the BWIP-JS API and encoded in the Code 128 format.

---

## Purpose

The generated barcode allows each shipment label to be uniquely identified and scanned during downstream processes.

---

## Barcode Format

- Standard: Code 128
- Generation: BWIP-JS API
- Source Value: Production Order (OB)

---

## AppSheet Expression

```appsheet
CONCATENATE(
  "https://bwipjs-api.metafloor.com/?bcid=code128&text=",
  ENCODEURL([OB_ID]),
  "&height=8"
)
```

---

## How It Works

1. Retrieves the current Production Order identifier.
2. Encodes the value for URL compatibility.
3. Sends the value to the BWIP-JS service.
4. Returns the generated barcode image.
5. Embeds the barcode into the PDF label.

---

## Dependencies

- LANÇAMENTOS
- PDF Template
- BWIP-JS API

---

## Business Value

Using dynamically generated Code 128 barcodes improves traceability, eliminates manual label identification and provides a standardized shipment identification process.
