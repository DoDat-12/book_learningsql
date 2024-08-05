# Chapter 17. Working with Large Databases

While relational databases face various challenges as data volumes continue to grow, there are strategies such as
partitioning, clustering, and sharding that allow companies to continue to utilize relational databases by spreading
data across multiple storage tiers and servers. Other companies have decided to move to big data platforms such as
Hadoop in order to handle huge data volumes.

## Partitioning

The following tasks become more difficult and/or time-consuming as a table grows past a few million rows:

- Query execution requiring full table scans

- Index creation/rebuild

- Data archival/deletion

- Generation of table/index statistics

- Table relocation (e.g., move to a different tablespace)

- Database backups

The best way to prevent administrative issues from occurring in the future is to break large tables into pieces, or
partitions, when the table is first created (although tables can be partitioned later, it is easier to do so initially)

Administrative tasks can be performed on individual partitions, often in parallel, and some tasks can skip one or more
partitions entirely

### Partitioning Concepts

When a table is partitioned, two or more table partitions are created, each having the exact same definition but with
non-overlapping subsets of data. For example, a table containing sales data could be partitioned by month using the
column containing the sale date, or it could be partitioned by geographic region using the state/province code

Once a table has been partitioned, the table itself becomes a virtual concept; the partitions hold the data, and any
indexes are built on the data in the partitions

> The database users can still interact with the table without knowing that the table had been partitioned (similar to a
> view, users interact with schema objects that are interfaces rather than actual tables)

While every partition must have the same schema definition (columns, column types, etc.), there are several
administrative features that can differ for each partition

- Partitions may be stored on different tablespaces, which can be on different physical storage tiers

- Partitions can be compressed using different compression schemes

- Local indexed can be dropped for some partitions

- Table statistics can be frozen on some partitions, while being periodically refreshed on others

- Individual partitions can be pinned into memory or stored in the database's flash storage tier

### Table Partitioning

