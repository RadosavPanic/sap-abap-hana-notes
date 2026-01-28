# CDS Repository Objects and Views

CDS uses two new repository objects: `Data Definition (DDL Source)` and `Access Control (DCL Source)`.

CDS views are defined in **DDL Source** and can only be developed in **ABAP Development Tool (ADT) in Eclipse**, not in classical ABAP Workbench.

After activation of a DDL Source, two objects are created:

- **SQL View** – visible in ABAP Dictionary, not editable, limited information
- **CDS View** – contains semantic information, not stored in the database, not visible in Dictionary, but consumable via `New OPEN SQL`

Each CDS view has a corresponding SQL view automatically generated. CDS views require `New OPEN SQL (NetWeaver 7.40+)` for access.

SQL views require explicit client handling, CDS views do not.

The simplest CDS view is a **projection** (field selection from a single table).

CDS is written in **SQL DDL** syntax but works across all databases.

CDS entities are defined using `DEFINE VIEW`.

`IMPORTANT` DDL source name and CDS view name should be identical.

## Annotations

**Annotations (`@`)** enrich CDS with metadata (buffering, client handling, semantics, etc.).

CDS views are **client-dependent by default**.

Mandatory annotation: `@AbapCatalog.sqlViewName`.

Optional annotations:

- `@AbapCatalog.buffering.status`: #ACTIVE (default value)
- `@AbapCatalog.buffering.type`: #SINGLE (default value)
- `@ClientDependent`: true (default value)

### CDS View Example

DDL Source (File name): ‘Z_CDS_DDL_Example1’

`@AbapCatalog.sqlViewName`: ‘Z_CDS_SQL_Example1’

`@EndUserText.label`: ‘Simple CDS View’ // used for description, displayed next to DDL Source name

`define view` Z_CDS_DDL_Example1 `as`

`select from` scarr

`{`

carrid `as` Airline_Code,

carrname `as` Airline_Name,

currcode `as` Currency_Code,

url `as` Airline_URL

`}`

## Types of Annotations

Based on scope of annotations, they can be divided in 5 groups:

- View annotations
- Element annotations
- Parameter annotations
- Extension annotations
- Function annotations

### View Annotations

View annotations are annotations for CDS Views and are used in front of `DEFINE VIEW` to define different view options.

Examples:

- `@AbapCatalog.sqlViewName`: 'Z_CDS_SQL_Example1'
- `@EndUserText.label`: 'Description of CDS View'

### Element Annotations

Used for targeting individual elements in the `SELECT` list. Placed before or after the field.

Examples:

- `@Semantics.amount.currencyCode`: 'local_currency_key'
- `@Semantics.currencyCode`: true

### Parameter Annotations

Used for view parameters. Placed before or after the parameter declaration.

Examples:

- `@Environment.systemfield`: #SYSTEM_DATE
- `@Consumption.filter.selectionType`
- `@Analytics.filterRange`
  ​

### Extension Annotations

Used for extending CDS views. Placed before the `EXTEND VIEW` statement.

Examples:

- `AbapCatalog.sqlViewAppendName`: 'Z_CDS_SQL_Example_number"
- `@AbapCatalog.extension.version`
  ​

### Function Annotations

Used for CDS table functions. Placed before the `DEFINE TABLE FUNCTION` statement.

Examples:

- `@Analytics.dataExtraction.enabled`
