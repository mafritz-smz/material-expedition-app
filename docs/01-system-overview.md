# System Overview

## Purpose

Material Expedition App is an application developed to control the expedition of industrial materials through barcode scanning.

Instead of manually checking production orders, the application validates every scanned piece against the expected production data, reducing operational errors and improving traceability.

The system was designed to support operators during the expedition process by ensuring that each scanned piece belongs to the correct production order.

---

## Process Overview

The workflow begins when production orders are imported from the production planning system (PCP).

Each production order defines:

- Machine
- Production lot
- Material
- Color
- Required quantity (Barca)

During the expedition process, operators scan each piece individually.

For every scan, the application validates whether the piece belongs to the selected production order.

Only valid pieces are registered.

When the required quantity is reached, the application automatically generates the labels for that production order.

---

## Main Components

The application is organized into three core datasets.

### BASE PCP

Stores all production orders available for expedition.

Each record represents one production order.

---

### BASE MATERIAIS

Stores the master data for every individual piece that can be scanned.

This table contains the production information used during validation.

---

### LANÇAMENTOS

Stores every barcode scan performed by operators.

Each record represents one scanned piece linked to a production order.

---

## Traceability

Every expedition is fully traceable.

Each scanned piece is recorded together with:

- Operator
- Date and time
- Production order
- Material
- Weight
- Color

Once completed, the system generates labels containing unique barcodes that can be used to identify the shipment.

---

## High-Level Workflow

```text
Production Orders

        │

        ▼

Select Production Order

        │

        ▼

Scan Piece

        │

        ▼

Validate

        │

        ▼

Register Scan

        │

        ▼

Required Quantity Reached?

        │

    Yes ▼

Generate Labels PDF

        │

        ▼

Print Labels
```
