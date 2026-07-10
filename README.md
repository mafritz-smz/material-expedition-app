# Material Expedition App

Material Expedition App is an industrial application developed in AppSheet to control the expedition of previously weighed materials through barcode scanning.

The system validates each scanned piece against the production order, ensuring that only materials belonging to the correct machine, lot and color are shipped.

Once the required quantity for a production order is reached, the application automatically generates a PDF containing the shipment labels, each with its own unique barcode for traceability.

---

## The Problem

Before this application, the expedition process depended on manual verification, making it susceptible to mistakes such as:

- Shipping pieces from the wrong machine
- Mixing production lots
- Sending incorrect colors
- Manual counting
- Manual label generation

These issues increased operator workload and reduced process reliability.

---

## The Solution

The application automates the entire expedition workflow.

Each production order defines what should be shipped. Operators simply scan the barcode of each piece, while the application validates all business rules automatically.

When the required quantity is completed, the labels are generated without any manual intervention.

---

## Main Features

- Production order management
- Barcode scanning
- Machine validation
- Lot validation
- Color validation
- Automatic weight calculation
- Shipment history
- Automatic PDF generation
- Label printing
- Traceability

---

## Technologies

- Google AppSheet
- Google Sheets
- AppSheet Expressions
- AppSheet Automation
- Google Drive
- PDF Templates

---

## Documentation

This repository documents every part of the application, including:

- Database modeling
- Business rules
- Table relationships
- Expressions
- Automations
- PDF generation
- Label template
