# IncrementalComputation
Papers, Surveys, and Related Materials for Incremental Computation

(Below is just a temporal classification. Please feel free to modify.)

### Dataflow System 
1. Naiad: A Timely Dataflow System [[Paper](https://dl.acm.org/doi/pdf/10.1145/2517349.2522738)] [[GitHub](https://github.com/frankmcsherry/timely-dataflow)][[Connected Papers](https://www.connectedpapers.com/main/98ca08bdb4092d59ef6efcedf8003239f89cf58f/Naiad%3A-a-timely-dataflow-system/graph)]
2. Differential dataflow [[Paper](http://michaelisard.com/pubs/differentialdataflow.pdf)] [[GitHub](https://github.com/TimelyDataflow/differential-dataflow)]
3. Declarative Dataflow [[GitHub](https://github.com/comnik/declarative-dataflow)]
4. It's About Time: An Introduction to Timely Dataflow | Clockworks [[YouTube List](https://www.youtube.com/watch?v=ZN7nOwJTSZ0&list=PLqs87sfbAM0EESOXJN0rP_hRHu3hRANcb&index=1)]

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
