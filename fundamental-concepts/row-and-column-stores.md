# Row and column store

**SAP HANA supports two table storage types: Row Store and Column Store, which define how two-dimensional tables are stored in linear main memory.**

## Row store

In a **row store**, all fields of a record are stored adjacently in memory, making it highly efficient for transactional scenarios where complete records are frequently accessed or modified.

This storage type is well suited for OLTP use cases where applications typically read or update one row at a time.

## Column store

In contrast to row store, a **column store** stores values of each column sequentially in adjacent memory locations.

This design is optimized for analytical queries that access only a subset of columns, perform aggregations, or search based on values in specific columns.

Column stores pros:

- Minimizes memory usage by loading only required columns
- Improves CPU efficiency due to cache-friendly access patterns

- Often eliminates need for additional indexes

SAP HANA column store tables also support automatic data compression and are inherently optimized for parallel processing. Different CPU cores can process different columns or partitions of the same column simultaneously.

_ABAP Development Perspective use cases_

- Column store tables should be chosen for large datasets, analytical operations, aggregations, and searches on a limited number of columns

- Row store tables are preferable when applications frequently access complete records, process individual rows, or require simple transactional operations without aggregation or compression.
