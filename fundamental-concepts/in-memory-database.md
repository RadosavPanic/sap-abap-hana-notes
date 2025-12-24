# In-memory database

SAP HANA is an in-memory database platform that enables real-time **Hybrid Transactional and Analytical Processing** (HTAP), allowing both OLTP and OLAP on the same system.

**OLTP** (Online Transactions Processing) is **row based processing** that retrieves the data based on rows. 

- OLTPs are the original source of data, and all CRUD operations can be done on them - Add, Modify, Delete, Update and Read.
- Used in **Operative Environment** - control and run fundamental business tasks.
- Row based processing is faster in operative tasks - obtaining specific object’s data and modifying it in the memory
- Row based processing is slow for analytical purposes where different types of data are presented for each row

**OLAP** (Online Analytical Processing) is **column based processing** that retrieves the data based on columns. 

- OLAPs support Read operation only operation
- Used in **informative environment** - for planning, problem solving and decision support.
- Column based processing is faster to process and analyze data if each column has similar type of data
- Column based processing is slow for operative tasks - obtaining specific all data for object and modifying it

## Dynamic Tiering

Unlike traditional disk-based databases, SAP HANA stores data primarily in main memory, eliminating disk I/O bottlenecks and significantly improving read and write performance, 

Mandatory persistent storage layer is still needed for data recovery and overflow.

To optimize cost and performance, SAP HANA uses dynamic tiering: 

- Keeping frequently accessed HOT data in main memory
- Keeping less frequently accessed WARM data on disk, loading data into memory automatically when needed

By supporting both row-based tables for transactions and column-based tables for analytics, SAP HANA removes data redundancy and simplifies the approach by enabling transactional and analytical workloads on a single platform.

That way, only one copy of data is needed for both CRUD operations and analytical calculations.