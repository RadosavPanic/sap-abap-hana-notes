# Data compression

Data compression is a key feature of SAP HANA that reduces memory consumption and improves performance. This technique is usually used on column store tables.

Column store tables enable efficient compression, making it more cost-effective to keep large volumes of data in main memory while also accelerating searches and calculations. 

## Compression types

SAP HANA supports two types of compression: 

- **Dictionary compression** - applied by default to all columns
- **Advanced compression** - uses techniques such as prefix encoding, run-length encoding (RLE), cluster encoding, sparse encoding, and indirect encoding

Dictionary compression works by storing each distinct column value only once in a dictionary and replacing the actual values in the table with small integer value IDs. 

This significantly reduces memory usage, particularly for columns with repetitive or long string values. 

Instead of performing operations on the original data, SAP HANA processes the compressed values directly, avoiding decompression during query execution.

## 3 Major benefits of data compression

- Reduces the memory size
- Improves CPU cache efficiency by allowing more data to be loaded per cycle
- Speeds up comparisons by replacing expensive string comparisons with faster integer comparisons