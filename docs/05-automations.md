# Automations

## Overview

The application uses AppSheet Bots to automate critical steps of the expedition process.

Instead of requiring manual actions from the operator, the system reacts to specific events and executes predefined workflows.

The main automation is responsible for detecting when a production order has reached its required quantity and generating the corresponding labels.

---

# Scan Registration

The automation process begins when a barcode is successfully scanned.

After validation, a new record is created in the `LANÇAMENTOS` table.

This record contains all information required to update the expedition progress.

---

# Expedition Progress

Every new scan updates the current quantity associated with the selected Production Order.

The application compares:

- Current scanned quantity
- Required quantity (Barca)

This comparison determines whether the expedition is still in progress or has been completed.

---

# Completion Detection

When the scanned quantity reaches the required quantity, the application identifies the expedition as complete.

This event triggers the label generation workflow automatically.

No manual confirmation is required.

---

# PDF Generation

After completion is detected, the application generates a PDF document containing the shipment labels.

The document is created using an AppSheet template populated with data from the completed Production Order.

The generated PDF contains:

- Production Order
- Material
- Color
- Total Weight
- Unique barcode
- Shipment information

---

# File Storage

After the PDF is generated, the file is stored in the configured destination.

The Production Order is then updated with the generated document reference.

---

# Label Availability

Once the document has been created successfully, it becomes available for printing.

Operators do not need to manually prepare the labels.

---

# Automation Flow

```text
Successful Scan
        │
        ▼
Create Scan Record
        │
        ▼
Update Expedition Progress
        │
        ▼
Required Quantity Reached?
        │
    No ─────────► Wait for Next Scan
        │
       Yes
        │
        ▼
Generate PDF
        │
        ▼
Store Document
        │
        ▼
Enable Label Printing
```

---

# Benefits

The automation workflow provides:

- Reduced manual intervention
- Faster expedition process
- Automatic document generation
- Improved traceability
- Consistent label creation
