# CDS Case Conditional Expressions

ABAP CDS supports **CASE conditional expressions** starting from **Open SQL 7.40 SP05**.

CASE expressions can be used in the **element list of a SELECT statement**.

A CASE expression starts with `CASE` and ends with `END`, and it **always returns exactly one value**.

Each CASE expression **must have an alias**.

The condition is defined after `WHEN`, and the result is specified after `THEN`.

If none of the conditions are met, the `ELSE` branch is executed.

If `ELSE` is missing, the syntax check raises a warning.

## Types of Case Expressions

There are different types of CASE expressions:

- **Simple CASE**: result depends on the value of a reference field (similar to ABAP `CASE` statement)

Example:

`case` smoker

`when` ’X’ `then` loccuram + 100

`else` loccuram

`end as` inc_smoker_charge_1

- **Searched CASE**: result depends on logical conditions (similar to ABAP `IF` statement)

Example:

`case`

`when` smoker = ‘X’ `and` custtype = ‘B’ `then` loccuram + 200

`when` smoker = ‘X’ `and` custtype = ‘P’ `then` loccuram + 100

`else` loccuram

`end as` inc_smoker_charge_2

- **Nested CASE**: CASE expressions can be nested inside each other

Example:

`case` smoker

`when` ’ ‘ `then` loccuram

`else` `case`

           when smoker = ‘X’ and custtype = ‘B’ then loccuram + 200

           when smoker = ‘X’ and custtype = ‘P’ then loccuram + 100

           else loccuram

      end

`end as` inc_smoker_charge_3
