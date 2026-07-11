# Actions

## Overview

This document describes the AppSheet Actions used by the application.

Actions are responsible for updating data and preparing records used by automation workflows.

---

# Generate PDF Filename

## Target Table

BASE PCP

---

## Action Type

Data: set the values of some columns in this row.

---

## Purpose

Generates a unique filename that will be used to store the PDF generated after the expedition is completed.

---

## Updated Column

`ARQUIVO_ETIQUETA`

---

## AppSheet Expression

```appsheet
CONCATENATE(
  "arquivos/",
  [OB],
  "_",
  UNIQUEID(),
  ".pdf"
)
```

---

## How It Works

1. Uses the Production Order identifier.
2. Generates a unique identifier using `UNIQUEID()`.
3. Concatenates the values into a valid PDF filename.
4. Stores the resulting path in the `ARQUIVO_ETIQUETA` column.

---

## Example Output

```text
arquivos/123456_AB12CD34EF.pdf
```

---

## Dependencies

- BASE PCP
- Generate PDF Bot

---

## Business Value

Using a unique filename prevents collisions between generated documents and guarantees that each expedition produces its own PDF file.
