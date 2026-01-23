# Performance guidelines

To fully leverage SAP HANA’s capabilities, traditional ABAP programming paradigms and application designs must be adapted.

In classic ABAP development, common use case was to reduce database calls by fetching large datasets into the application server and processing them there. 

While this approach worked well for disk-based databases, it is not optimal for SAP HANA’s in-memory architecture.

SAP HANA uses `code-to-data` paradigm, where data-intensive logic is pushed down to the database layer. Instead of transferring large volumes of data to the application server, computations are executed directly in the database, and only the final result set is returned to the ABAP program, resulting in better performance and reduced data transfer.

## Five golden rules for optimizing ABAP programs

1. **`Keep the result set small`** - by using `WHERE` and `HAVING` clauses to reduce memory usage and network load. 
2. **`Minimize the amount of data transferred`** - by selecting only the required fields instead of using `SELECT *`. 
3. **`Minimize the number of database accesses`** - by avoiding nested `SELECT` loops and using joins or subqueries instead.
4. **`Minimize search overhead`** - by designing efficient filter conditions that align with table indexes. 
5. **`Reduce overall database load`** - by avoiding redundant data reads, using table buffering where appropriate, and performing sorting operations in the ABAP layer when it’s possible.

Following these principles ensures that ABAP applications are properly optimized for SAP HANA’s in-memory and high-performance environment.