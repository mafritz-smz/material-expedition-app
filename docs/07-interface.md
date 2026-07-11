# User Interface

## Overview

The application's interface was designed for operators working in an industrial environment.

The workflow prioritizes speed, minimizes manual interaction and reduces the possibility of operational errors.

Each screen has a specific responsibility within the expedition process.

---

# Production Orders

This is the application's main screen.

It displays every Production Order available for expedition.

For each order, the operator can quickly identify information such as:

- Production Order
- Material
- Machine
- Production Lot
- Color
- Required Quantity
- Current Progress

The expedition workflow begins by selecting one of these orders.

---

# Production Order Details

After selecting a Production Order, the operator is presented with all information required for the expedition.

Typical information displayed includes:

- Material
- Color
- Machine
- Lot
- Expected Quantity
- Total Weight

This screen also provides access to the scan history and expedition progress.

---

# Barcode Scanning

Barcode scanning is the primary interaction performed by the operator.

Each successful scan is automatically validated before being registered.

Manual data entry is intentionally minimized.

---

# Scan History

Every successful scan becomes part of the expedition history.

The scan history allows operators to verify:

- Scanned pieces
- Scan sequence
- Weight
- Material
- Color

This information also supports production traceability.

---

# Expedition Progress

The application continuously updates the expedition progress.

Operators can monitor:

- Current quantity
- Remaining quantity
- Total scanned weight

Once the required quantity is reached, the expedition is completed automatically.

---

# Label Printing

After the expedition is completed, the generated labels become available for printing.

The operator does not need to manually prepare the document.

The application automatically generates the PDF using the completed Production Order.

---

# Interface Design

The interface follows a simple navigation model.

```

Production Orders

↓

Production Order Details

↓

Barcode Scanning

↓

Scan History

↓

Automatic Label Generation

↓

Print Labels

```

---

# Design Principles

The interface was designed around the following principles:

- Minimal manual input.
- Fast navigation.
- Clear production information.
- Automatic validation.
- Immediate feedback.
- Operational simplicity.

These principles reduce operator workload while increasing reliability during the expedition process.
