# Business Rules

This document describes the business rules implemented by the application.

The goal of these rules is to ensure that only valid materials are shipped and that the expedition process remains consistent and traceable.

---

# Production Order

Every expedition starts from a production order (OB).

A production order defines:

- Machine
- Production Lot
- Material
- Color
- Required Quantity (Barca)

Operators cannot scan materials without first selecting a production order.

---

# Barcode Validation

Each scanned barcode is searched in the Material Database.

If the barcode is not found, the scan is rejected.

---

# Machine Validation

Every scanned piece must belong to the machine defined by the selected production order.

If the machine does not match, the scan is rejected.

---

# Lot Validation

The production lot of the scanned piece must match the lot defined in the production order.

If the lots are different, the scan is rejected.

---

# Material Validation

The scanned material must belong to the expected production order.

Unexpected materials are not accepted.

---

# Color Validation

The application validates the color associated with the scanned piece.

Only the expected color can be registered.

---

# Quantity Control

Every successful scan increases the quantity of scanned pieces for the selected production order.

The application constantly compares:

Scanned Quantity

with

Required Quantity (Barca)

---

# Expedition Completion

When the scanned quantity reaches the required quantity, the production order is considered complete.

At this point the application automatically starts the label generation process.

No manual confirmation is required.

---

# Automatic Label Generation

Once the expedition is completed:

- Labels are generated automatically.
- A PDF document is created.
- The file is stored.
- Labels become available for printing.

---

# Traceability

Every successful scan stores:

- Production Order
- Barcode
- Material
- Color
- Weight
- Operator
- Date
- Time

This information allows the complete reconstruction of any expedition.

---

# Data Integrity

The application minimizes manual data entry.

Most information is automatically retrieved from the Material Database after the barcode is scanned.

This reduces typing errors and increases process reliability.
