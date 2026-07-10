# BASE MATERIAIS

## Overview

The `BASE MATERIAIS` table is the application's master data source.

Each record represents a single production piece that can be identified through barcode scanning.

This table provides the information required to validate scanned materials during the expedition process.

Unlike operational tables, this dataset acts as a reference and is not modified during barcode scanning.

---

# Responsibility

The table is responsible for:

- Registering every available production piece.
- Identifying the production machine.
- Identifying the production lot.
- Storing the piece weight.
- Identifying the material.
- Identifying the color.
- Providing data for scan validation.

It serves as the source of truth for every barcode scanned by the application.

---

# Relationships

```
BASE MATERIAIS

        │

        ▼

Barcode Scan

        │

        ▼

LANÇAMENTOS
```

The application searches this table whenever a barcode is scanned.

If the barcode exists, its information is used during validation.

---

# Main Columns

| Column | Description |
|---------|-------------|
| MÁQUINA | Production machine associated with the piece. |
| CÓDIGO PEÇA | Unique identifier used during barcode scanning. |
| PESO | Individual piece weight. |
| LOTE | Production lot. |
| DATA/HORA | Record creation date. |
| OBSERVAÇÃO | Additional information about the piece. |
| TECIDO | Material or fabric description. |
| SOMA | Reference value used in weight calculations. |

---

# Usage During Scanning

When the operator scans a barcode, the application searches this table.

If a matching record is found, the application retrieves:

- Machine
- Lot
- Weight
- Material
- Color

This information is then compared with the selected Production Order.

---

# Validation Source

The data stored in this table supports the application's validation rules.

The scanned piece is accepted only if its information matches the expected Production Order.

Typical validations include:

- Machine
- Lot
- Material
- Color

---

# Data Integrity

Operators do not manually enter material information during the expedition process.

The barcode alone is sufficient to retrieve all required production data.

This approach minimizes manual input and improves process reliability.

---

# Notes

The `BASE MATERIAIS` table is not intended to store expedition history.

Its purpose is to provide accurate reference data for barcode validation throughout the application.
