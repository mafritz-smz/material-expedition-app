# AppSheet Structure

## Overview

The application was developed using Google AppSheet with a relational data model and event-driven automations.

Instead of relying on custom code, the system leverages AppSheet features such as references, virtual columns, expressions, bots and document templates to automate the expedition workflow.

---

# Data Sources

The application is connected to Google Sheets.

Each worksheet represents one dataset inside AppSheet.

Current datasets:

- BASE PCP
- BASE MATERIAIS
- LANÇAMENTOS

---

# Views

The application is organized into different views to guide the operator through the expedition process.

## Production Orders

Displays every production order available for expedition.

Operators start the process by selecting one order.

---

## Production Order Details

Displays all information related to the selected production order.

This screen includes:

- Material information
- Machine
- Lot
- Color
- Required quantity
- Total weight
- Scan history

It also provides access to barcode scanning.

---

## Scan Records

Displays every scanned piece associated with the selected production order.

Each scan becomes part of the expedition history.

---

# References

The application uses Ref columns to establish relationships between datasets.

Example:

Production Order

↓

Multiple Scan Records

This allows AppSheet to automatically display related scans inside each production order.

---

# Virtual Columns

Virtual Columns are used to calculate information dynamically.

Examples include:

- Total scanned pieces
- Total scanned weight
- Remaining quantity
- Related scan records

These values are calculated automatically and are not stored permanently.

---

# Expressions

Business logic is implemented through AppSheet Expressions.

Expressions are responsible for:

- Data validation
- Automatic lookups
- Calculations
- Conditional logic
- Data retrieval

The implementation details are documented separately.

---

# Actions

The application includes actions that simplify the operator workflow.

Examples:

- Add new scan
- Open production order
- Print labels

Actions reduce navigation and improve usability.

---

# Bots

AppSheet Bots automate repetitive tasks.

Current automation includes:

- Detect completed expedition
- Generate PDF labels
- Save generated document

Bots are triggered automatically according to business rules.

---

# Security

The application minimizes manual data entry.

Most fields are automatically populated from existing datasets after the barcode is scanned.

This approach reduces typing errors and improves data consistency.

---

# User Experience

The interface was designed for operators working in an industrial environment.

The workflow minimizes the number of manual interactions required to complete an expedition.

Operators mainly perform two actions:

1. Select a production order.

2. Scan each piece.

All remaining validations and calculations are handled automatically by the application.
