# Generate PDF

## Overview

This Bot automatically generates shipment labels when a Production Order reaches its required quantity.

The automation eliminates manual document creation and ensures that every completed expedition receives its corresponding PDF label.

---

## Trigger

The Bot is triggered whenever the number of scanned pieces becomes equal to the required quantity defined in the selected Production Order.

## Trigger Expression

```appsheet
COUNT(
  SELECT(
    LANÇAMENTOS[ID],
    [OB_ID] = [_THISROW].[OB_ID]
  )
)
=
[_THISROW].[OB_ID].[PEÇAS]
```

---

## Process

After the trigger condition is satisfied, the Bot locates the corresponding Production Order using:

```appsheet
FILTER(
  "BASE PCP",
  [OB] = [_THISROW].[OB_ID]
)
```

The selected record becomes the source for the PDF generation process.

---

## Output

The generated document contains one shipment label for each scanned piece associated with the completed Production Order.

---

## Dependencies

- BASE PCP
- LANÇAMENTOS
- PDF Template

---

## Business Value

Automating PDF generation removes manual intervention, guarantees document consistency and improves expedition traceability.
