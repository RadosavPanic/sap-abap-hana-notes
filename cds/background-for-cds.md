# Background for CDS

When accessing a database management system from application programming, **`SQL (Structured Query Language)`** has established itself as the standard and most widely used approach.

SQL is divided into three main sublanguages, each responsible for a different aspect of database interaction.

## SQL Sublanguages

1. **`Data Manipulation Language (DML)` -** provides statements for reading and modifying the contents of database tables. Typical DML statements include `SELECT`, `INSERT`, `UPDATE`, and `DELETE`.
2. **`Data Definition Language (DDL)` -** used to define and manage database objects and their properties. This includes statements such as `CREATE TABLE`, `CREATE VIEW`, `ALTER TABLE`, and `DROP TABLE`.
3. **`Data Control Language (DCL)` -** focuses on data security and integrity. It includes statements like `GRANT` and `REVOKE`, which control access permissions to database objects.

## Open SQL in ABAP

In the ABAP programming environment, database access is traditionally done using **Open SQL**.

Open SQL is SAP’s database-independent SQL variant embedded directly into the ABAP language. However, Open SQL supports **only Data Manipulation Language (DML)** operations.

When an ABAP developer needs to define database tables or views, **DDL statements are not executed at runtime**.

Instead, developers use `ABAP Dictionary tools`, which provide form-based editors for defining database objects such as transparent tables and database views. During the activation of these dictionary objects, the ABAP system automatically generates database-specific DDL statements and sends them to the underlying database.

## Classical Open SQL Limitations

Classical Open SQL has several functional limitations, especially when compared to modern SQL capabilities. Many important DML features are missing.

For example, classical Open SQL does not support:

- Fixed values and computed columns
- `CASE` expressions
- Right outer joins
- `UNION` and `UNION ALL`
- Subqueries in the `SELECT` list or in the `FROM` clause

In addition, classical Open SQL cannot access `SAP HANA specific features`, such as built-in functions, calculation views, or database procedures.

Most importantly, it does not fully support the **code push-down approach**, which is essential for taking advantage of SAP HANA’s in-memory processing power.

## New Open SQL

To overcome classical Open SQL limitations, SAP introduced **New Open SQL**, available from **ABAP NetWeaver 7.40 SP05** and further versions.

New Open SQL significantly enhances power of SQL statements and enables processing directly at the database level.

New Open SQL supports:

- Arithmetic expressions using addition, subtraction, multiplication, and division
- Arithmetic functions such as `FLOOR`, `CEIL`, `MOD`, `ABS`, and `DIV`
- `CASE` expressions
- Right outer joins
- `UNION` and `UNION ALL`

Additionally, maximum number of tables in a join has been increased `from 9 to 50`, and the number of supported subqueries has increased `from 9 to 50`.

With New Open SQL, ABAP programs can also access **SAP HANA built-in functions, views, and procedures**, enabling true code push-down.
