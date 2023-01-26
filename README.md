# IncrementalComputation
Papers, Surveys, and Related Materials for Incremental Computation

(Below is just a temporal classification. Please feel free to modify.)

### Dataflow System

### Event Processing
1. Recent Advancements in Event Processing [[Survey](https://dl.acm.org/doi/pdf/10.1145/3170432)]

### Streaming SQL Query Optimizers

### To Be Classified...
1. Live Tables and Delta Live Tables
* Delta Live Tables: Modern Software Engineering and Management for ETL [[Intro on Youtube](https://www.youtube.com/watch?v=zo6K6g2jfqY)]
* Process streaming data with Delta Live Tables [[Link](https://learn.microsoft.com/en-us/azure/databricks/workflows/delta-live-tables/delta-live-tables-incremental-data)]
* Delta Live Tables concepts [[Link](https://docs.databricks.com/workflows/delta-live-tables/delta-live-tables-concepts.html)]
  > A __live table or view__ always reflects the results of the query that defines it, including when the query defining the table or view is updated, or an input data source is updated. Like a traditional materialized view, a live table or view may be __entirely computed__ when possible to optimize computation resources and time.
  
  > A __streaming live table or view__ processes data that has been __added only__ since the last pipeline update. Streaming tables and views are stateful; if the defining query changes, new data will be processed based on the new query and existing data is not recomputed.
2. Dynamic Tables in Flink
* Dynamic Tables: Intro and Definitions [[Link](https://nightlies.apache.org/flink/flink-docs-master/docs/dev/table/concepts/dynamic_tables/)]
* 
