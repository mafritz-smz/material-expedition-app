# Scan Validation

## Overview

The application validates every scanned piece before creating a new expedition record.

Validation is implemented through a single `IFS()` expression that evaluates multiple business rules sequentially.

The first matching condition stops the validation process and returns the corresponding message.

---

## Validation Rules

### 1. Maximum Quantity Reached

The application prevents additional scans after the required quantity defined by the Production Order has been reached.

Message:

```
❌ Limite de peças atingido
```

---

### 2. Duplicate Piece in the Same Production Order

A piece cannot be scanned twice within the same Production Order.

Message:

```
❌ Peça já lançada nessa OB
```

---

### 3. Duplicate Piece in Another Production Order

A piece associated with the same machine cannot belong to multiple Production Orders.

Message:

```
❌ Esta peça desta máquina já foi lançada em outra OB
```

---

### 4. Missing Material Information

If the scanned barcode cannot retrieve a valid weight from the material database, the scan is rejected.

Message:

```
❌ Peça não encontrada / sem peso cadastrado
```

---

### 5. Black Material Validation

Pieces identified as black ("PRETO") cannot be scanned into Production Orders intended for another color.

Message:

```
❌ Peça para PRETO não pode ser lançada em OB de cor
```

---

### 6. Machine Validation

The scanned piece must belong to the same production machine defined by the selected Production Order.

Message:

```
❌ A máquina dessa peça bipada é diferente da OB selecionada
```

---

## Implementation

The complete validation is implemented using an AppSheet `IFS()` expression.

The expression combines `SELECT()`, `COUNT()`, `CONTAINS()`, `STARTSWITH()`, `TRIM()` and logical operators to guarantee data integrity during the expedition process.
