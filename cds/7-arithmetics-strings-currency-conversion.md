# CDS Arithmetics, String Expressions and Currency Conversion in CDS Views

## Arithmetic expressions

Arithmetic expressions can be used as `elements of the field`.

ABAP CDS supports arithmetic expressions such as `addition`, `subtraction`, `multiplication` and `division`.

It also supports built-in functions such as:

- `abs`**(a1)**: returns absolute value of a1
  Example:
  abs(-2.5) = 2.5

- `floor`**(a1)**: returns to the next lower integer
  Example:
  floor(2.5) = 2
  floor(-2.5) = -3

- `ceil`**(a1)**: returns to the next higher integer
  Example:
  ceil(2.5) = 3
  ceil(-2.5) = -2

- `round`**(a1, pos)**: round a1 to pos decimal places
  Example:
  round(4.9514, 2) = 4.95

### Casting values

Unlike ABAP, ABAP CDS doesn't know implicit type conversions. Therefore, we need to use built-in function `CAST`.

`CAST`**(operand AS target type)**: converts the value of operand into target type

Target type can be:

- Predefined dictionary type: e.g. `abap.int4`, `abap.char(10)`, `abap.dec(8, 2)`
- Any dictionary data element: e.g. `S_CARR_ID`, `S_CUSTOMER`

Operand can be:

- Literal (without a domain prefix)
- Field of a data source
- Arithmetic expression
- Case expressions with `CASE`
- Predefined function
