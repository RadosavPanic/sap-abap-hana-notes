# Multi-core architecture

Key feature of SAP HANA is its multi-core architecture, which enables efficient parallel processing.

Modern CPUs consist of multiple cores that can process data independently or simultaneously, allowing SAP HANA to handle large volumes of data in parallel.

As disk I/O bottlenecks are removed by in-memory processing, performance challenges shift to CPU cache efficiency and data transfer between main memory and the CPU.

SAP HANA tackles these challenges by optimizing data loading to minimize cache misses and by fully utilizing all CPU cores through parallel execution, preventing idle resources and maximizing hardware performance.

## Parallel Processing

Parallel processing is a core performance enabler of SAP HANA, leveraging modern multi-core hardware to deliver real-time responses.

SAP HANA automatically distributes workloads across all available CPU cores, ensuring optimal utilization of system resources and preventing idle hardware.

The platform is highly scalable, allowing additional processors to be added to increase parallelization and processing speed.

By using column-store tables, SAP HANA enables automatic parallel execution, where individual columns, or even parts of the same column are processed simultaneously by multiple cores, maximizing processing speed of the data.