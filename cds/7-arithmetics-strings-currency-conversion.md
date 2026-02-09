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

## Built-in functions for string processing

String expressions are supported in ABAP CDS and here are some built-in functions:

- `concat`**(a1, a2)**: concatenates two strings, returns result of type `CHAR` or `STRING`.
  Corresponds to ABAP statement `CONCATENATE` without addition `SEPARATED BY`
- `replace`**(a1, a2, a3)**: Result type depends on a1. Inside a1 string, it replaces all a2 occurences with a3.
  Corresponds to ABAP statement `REPLACE ALL OCCURENCES` of a2 inside a1 with a3.
- `substring`**(a1, position, length)**: Result type depends on type of a1. Function looks into a1 string, and based on 2nd position argument and 3rd length argument, it returns sliced string - substring.
  Similar to **ABAP function substring()** or `direct substring access`.
- `length`**(a1)**: Returns length of the string, with result of type `INT4`.
  Corresponds to ABAP function `numofchar()`.

## Built-in functions for currency and unit processing

To make values in different units or currencies comparable with each other, they need to be converted.

### Unit Conversion

`unit_conversion`(**quantity** => a1,
**source_unit** => a2,
**target_unit** => a3)

Unit conversion returns result of type `abap.quan` for quantity.
Converts a quantity in source unit into a value in target unit. Rules are maintained in transaction CUNI and stored in database table T006.

### Currency Conversion

`currency_conversion`(**amount** => a1,
**source_currency** => a2,
**target_currency** => a3,
**exchange_rate_date** => a4)

Currency conversion returns result of type `abap.curr` for currency.
Converts an amount in source currency into a value in target currency, based on date of exchange rate. Rules are maitained in transaction OB08 and stored in database tables TCUR.
