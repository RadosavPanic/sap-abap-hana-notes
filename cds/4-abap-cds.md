# ABAP CDS

ABAP CDS were not designed exclusively for SAP HANA and support all database systems.

Since ABAP Dictionary already provided tables, views, and data types, CDS was introduced as **an extension** to the `ABAP Dictionary`.

ABAP CDS introduces new repository objects: `Data Definition (DDL Source)` and `Access Control (DCL Source)`, enabling code push-down and complex data processing at the database level, which was not possible with classical ABAP Dictionary views.

ABAP CDS views are read-only and cannot be used to modify data.

## ABAP Dictionary vs ABAP CDS Views

Support on all DMBS:

- Dictionary View: Yes
- CDS View: Yes

Support combining queries:

- Dictionary View: Inner Join
- CDS View: Inner Join, Outer Joins, Union

Calculation:

- Dictionary View: No
- CDS View: Aggregation, grouping, calculation expression

Nested Views (View-on-View):

- Dictionary View: No
- CDS View: Yes

While Dictionary views only project data, CDS views allow processing data directly in the database before returning results.

Key features of ABAP CDS include database independence, extended SQL capabilities, annotations for semantic enrichment, implicit authorization checks using DCL, associations instead of static joins, and support for CDS table functions using ABAP Managed Database Procedures.
