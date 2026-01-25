# CDS Views

Core Data Services are a collection of domain specific languages and services for defining and consuming semantically rich data models.

In ABAP terms, semantics are comparable to a Data Element, which defines labels and descriptions, while technical properties such as data type and length are defined by a Domain.

Data models are the foundation of application development. They provide a standardized way to define and structure database content.

In ABAP, this role is fulfilled by the `ABAP Data Dictionary`, which stores definitions of database tables, views, and their mapping to the underlying database.

Core Data Services consist of three domain-specific languages:

- `Data Definition Language (DDL)`
- `Query Language (QL)`
- `Data Control Language (DCL)`

`Data Definition Language (DDL)` part of CDS is an enhancement of SQL that allows defining semantically rich database tables, views, and user-defined types. These database objects are referred to as CDS entities.

`Query Language (QL)` enables CDS views defined using DDL to be consumed in ABAP programs using OPEN SQL or by other CDS views.

`Data Control Language (DCL)` is used to define authorizations for CDS entities. CDS authorization is based on implicit checks automatically performed by the ABAP runtime when CDS entities are accessed using OPEN SQL, and it can be used independently or together with classical authorization concepts.

## Types of CDS Views

Core Data Services (CDS) can be developed on multiple SAP platforms such as:

- ≥ **SAP NetWeaver 7.4 SP05**
- **≥ SAP HANA SPS06**
- **≥ SAP Business Warehouse 7.3**
- **SAP Business Suite EHP7 (Suite on HANA)**
- **S/4HANA**.

There are two types of CDS: `ABAP CDS` and `HANA CDS`.

### ABAP CDS

- Supports all DBs (e.g. Oracle, HANA)
- It’s located on ABAP Application Server
- Designed to support implementation of database-independent ABAP applications
- Initial focus on View Building

### HANA CDS

- Supports only HANA DBs
- It’s located on SAP HANA database directly
- Designed to support SAP HANA native application development (SAP HANA XS)
- Initial focus on building models from scratch
