# Aggregations in CDS Views

Aggregation functions are used to transform and display different results of data.
Types of aggregations in CDS:

- `MIN`(operand): Returns smallest value in operand
- `MAX`(operand): Returns higher value in operand
- `SUM`(operand): Calculates the sum of values of operand
- `AVG`(operand): Calculates the average value of the values of operand
- `COUNT`(\*): Returns the number of entries in the result set. Value is always of integer type
- `COUNT`(`DISTINCT` operand): Returns number of distinct values of operand. Value is always of integer type

Operand can be:

- Field of the data source
- Literal
- Case Expression

Any elements not covered by aggregation functions have to be used in pair with:

- `GROUP BY`: All elements not defined using aggregate functions must be specified after GROUP BY.
- `HAVING`: The HAVING clause is used to restrict the results returned by the GROUP BY clause.
