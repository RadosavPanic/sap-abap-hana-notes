# Need for CDS

SAP HANA can be used in different architectural scenarios. 

In one scenario, SAP HANA functions as a database connected to an application server. 

In another scenario, SAP HANA works as a standalone system where applications are developed and executed directly on the database without an application server.

To take advantage of SAP HANA’s capabilities, especially the code-push-down approach, developers need a way to define and consume data models directly at the database layer. 

From an ABAP developer’s perspective, this led to the introduction of **Core Data Services (CDS)**, which allow data-intensive logic to be executed on the database rather than on the application server.

## CDS in ABAP Application Layer

Originally, CDS was available only in the SAP HANA environment. 

Later, it was fully integrated into the SAP NetWeaver Application Server, enabling ABAP developers to work in the ABAP layer using ADT while pushing execution to the database.

## CDS Goal

CDS provides a structured data modeling repository on the database that goes beyond basic SQL statements like `CREATE TABLE` and `CREATE VIEW`, allowing technical definitions to be enriched with semantics.

CDS addresses common needs for both ABAP and HANA developers by providing a unified, semantically rich data modeling approach. It simplifies and enhances data model definitions across different technologies.

Technically, Core Data Services is an enhancement of SQL that provides DDL for defining semantically rich tables, views, and user-defined types in the database.