# LANÇAMENTOS

## Overview

The `LANÇAMENTOS` table records every successful barcode scan performed during the expedition process.

Each record represents a single scanned piece associated with a Production Order.

Unlike the master data tables, this dataset grows continuously as operators perform scans, becoming the application's operational history.

---

# Responsibility

The table is responsible for:

- Recording every successful scan.
- Associating each scan with a Production Order.
- Storing the scanned barcode.
- Recording the operator responsible for the scan.
- Recording the date and time of the operation.
- Preserving expedition traceability.

This table represents the execution of the expedition process.

---

# Relationships

```
BASE PCP

    │
    │ One
    ▼

LANÇAMENTOS

    ▲

    │ Lookup / Validation

BASE MATERIAIS
```

Each record in `LANÇAMENTOS` belongs to a single Production Order.

Information related to the scanned barcode is retrieved from `BASE MATERIAIS`.

---

# Main Columns

| Column | Description |
|---------|-------------|
| ID | Unique identifier for the scan record. |
| OB_ID | Reference to the associated Production Order. |
| PEÇA | Scanned barcode or piece identifier. |
| DATA/HORA | Date and time of the scan. |
| USUÁRIO | Operator responsible for the scan. |
| PESO | Weight retrieved from the material database. |
| MATERIAL | Material associated with the scanned piece. |
| COR | Color associated with the scanned piece. |
| MÁQUINA | Machine associated with the scanned piece. |
| LOTE | Production lot associated with the scanned piece. |
| BARCODE | Generated barcode used for traceability. |

---

# Record Creation

A new record is created only after the scanned barcode passes all business validations.

Typical validations include:

- Barcode exists.
- Correct machine.
- Correct production lot.
- Correct material.
- Correct color.

If any validation fails, the scan is not registered.

---

# Data Retrieval

Most values stored in this table are automatically obtained from the master datasets.

The operator is only responsible for scanning the barcode.

The application retrieves all remaining information automatically.

---

# Traceability

Each record preserves the complete history of the expedition.

The stored information allows future identification of:

- What was scanned.
- When it was scanned.
- Who performed the scan.
- Which Production Order received the piece.

---

# Usage

The information stored in this table is used by:

- Expedition progress calculation.
- Quantity control.
- Weight calculation.
- Shipment history.
- PDF generation.
- Label generation.
- Production tracking.

---

# Notes

The `LANÇAMENTOS` table is the application's transactional dataset.

It connects the planning defined in `BASE PCP` with the reference data stored in `BASE MATERIAIS`, creating a complete and traceable record of the expedition process.
