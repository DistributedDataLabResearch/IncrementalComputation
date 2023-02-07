# Incremental Computation
Papers, Surveys, and Related Materials for Incremental Computation

(Below is just a temporal classification. Please feel free to modify.)

## Event Processing (stream processing)
1. Recent Advancements in Event Processing [[Survey](https://dl.acm.org/doi/pdf/10.1145/3170432)]
* > 6.4 Out-of-Order Event Processing

  > Out-of-order event arrival is present in general data stream processing applications. Out-of-order
  events in a stream are produced due to multiple reasons such as operator parallelization, network
  latency, merging of asynchronous streams, etc [108]. Order-less event processing may result in
  a system failure. Handling the disorder consists of a trade-off between result latency and result
  accuracy. There are four main techniques of disorder handling: Buffer-based, Punctuation-based,
  Speculation-based, and Approximation-based.

## Stream Programming Model

### Timely DataFlow
0. Incremental, iterative data processing with timely dataflow [[paper](https://dl.acm.org/doi/pdf/10.1145/2983551)]
1. Naiad: A Timely Dataflow System [[Paper](https://dl.acm.org/doi/pdf/10.1145/2517349.2522738)] [[GitHub](https://github.com/frankmcsherry/timely-dataflow)][[Connected Papers](https://www.connectedpapers.com/main/98ca08bdb4092d59ef6efcedf8003239f89cf58f/Naiad%3A-a-timely-dataflow-system/graph)] [[ppt](https://www.cl.cam.ac.uk/~ey204/teaching/ACS/R244_2019_2020/presentation/S2/stefan_NAIAD.pdf)]
2. Differential dataflow [[Paper](http://michaelisard.com/pubs/differentialdataflow.pdf)] [[GitHub](https://github.com/TimelyDataflow/differential-dataflow)]
3. Declarative Dataflow [[GitHub](https://github.com/comnik/declarative-dataflow)]
4. It's About Time: An Introduction to Timely Dataflow | Clockworks [[YouTube List](https://www.youtube.com/watch?v=ZN7nOwJTSZ0&list=PLqs87sfbAM0EESOXJN0rP_hRHu3hRANcb&index=1)]
5. Differential Datalog (DDlog) [[website](https://research.vmware.com/projects/differential-datalog-ddlog)][[github](https://github.com/vmware/differential-datalog)]
> DDlog is a programming language for incremental computation, for writing programs that continuously update their output in response to changes.
6. What’s inside Materialize? An architecture overview [[blog](https://materialize.com/blog/architecture/#differential-dataflow)]



### Dataflow Model
 > (Databricks) Structured Streaming adopts the definitions of event time, processing time, watermarks and triggers from __Dataflow__ but incorporates them in an incremental model.

 > There were two main reasons for Flink’s rise to prominence:
  Its rapid adoption of the __Dataflow__/Beam programming model, which put it in the position of being the most semantically capable fully open source streaming system on   the planet at the time.

1. The Dataflow Model: A Practical Approach to Balancing Correctness, Latency, and Cost in Massive-Scale, Unbounded, Out-of-Order Data Processing [[paper](https://static.googleusercontent.com/media/research.google.com/zh-CN//pubs/archive/43864.pdf)] [[zhihu](https://zhuanlan.zhihu.com/p/54739130)]
2. Structured Streaming: A Declarative API for Real-Time Applications in Apache Spark [[paper](https://dl.acm.org/doi/pdf/10.1145/3183713.3190664)] [[jira](https://issues.apache.org/jira/browse/SPARK-20928)] [[doc](https://spark.apache.org/docs/latest/structured-streaming-programming-guide.html)] [[zhihu](https://zhuanlan.zhihu.com/p/51883927)] 
3. 

### Temporal Query Model
1. Trill: A High-Performance Incremental Query Processor for Diverse Analytics (VLDB'14) [[paper](http://www.vldb.org/pvldb/vol8/p401-chandramouli.pdf)]

## 🔥 OLVM (online view maintainance) 
1. incremental recomputation of active relational expressions (TKDE'91) [[paper](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=91063)]
2. Incremental Maintenance of Views with Duplicates (SIGMOD' 95) [[paper](https://homepages.inf.ed.ac.uk/libkin/papers/sigmod95.pdf)]
3. Incremental Maintenance for Analytics [[website](https://fdbresearch.github.io/ivm.html)]

## 🔥 States Management
1. Delta Joins and Late Materialization: Understand how to optimize joins with indexes and late materialization [[blog](https://materialize.com/blog/delta-joins/)]
2. What consistency guarantees should you expect from your streaming data platform? [[blog](https://materialize.com/blog/consistency/)]
> In-order reliable message delivery is not enough. Showing views over streams of data requires thinking through additional consistency semantics to deliver correct results.
3. Databricks: Delta Live Table [[blog](https://blogs.perficient.com/2022/07/11/top-5-take-aways-from-databricks-data-ai-summit-2022/)][[youtube](https://www.youtube.com/watch?v=zo6K6g2jfqY)]
> Announcing __Enzyme__, a new optimization layer designed specifically to speed up the process of doing ETL – Transforming data to prepare it for downstream analysis is a prerequisite for most other workloads on the Databricks platform. While SQL and Data frames make it relatively easy for users to express their transformations, the input data constantly changes. This requires re-computation of the tables produced by ETL. Enzyme is a a new optimization layer for ETL. Enzyme efficiently keeps up to date a materialization of the results of a given query stored in a Delta table. It uses a cost model to choose between various techniques, including techniques used in traditional materialized views, delta-to-delta streaming, and manual ETL patterns commonly used by data engineers.
4. Shared Arrangements: practical inter-query sharing for streaming dataflows (VLDB' 20) [[paper](https://people.csail.mit.edu/malte/pub/drafts/2019-kpg.pdf)]
5. Noria: dynamic, partially-stateful data-flow for high-performance web applications (OSDI' 18) [[paper](https://www.usenix.org/conference/osdi18/presentation/gjengset)] [[github](https://github.com/mit-pdos/noria)] [[previous version (SOSP short paper)](https://src.acm.org/binaries/content/assets/src/2018/jon-gjengset.pdf)]


## 


## Streaming SQL Query Optimizers
1. A catalog of stream processing optimizations [[paper](https://dl.acm.org/doi/10.1145/2528412)]


### To Be Classified...
1. Live Tables and Delta Live Tables
* Delta Live Tables: Modern Software Engineering and Management for ETL [[Intro on Youtube](https://www.youtube.com/watch?v=zo6K6g2jfqY)]
* Process streaming data with Delta Live Tables [[Link](https://learn.microsoft.com/en-us/azure/databricks/workflows/delta-live-tables/delta-live-tables-incremental-data)]
* Delta Live Tables concepts [[Link](https://docs.databricks.com/workflows/delta-live-tables/delta-live-tables-concepts.html)]
  > A __live table or view__ always reflects the results of the query that defines it, including when the query defining the table or view is updated, or an input data source is updated. Like a traditional materialized view, a live table or view may be __entirely computed__ when possible to optimize computation resources and time.
  
  > A __streaming live table or view__ processes data that has been __added only__ since the last pipeline update. Streaming tables and views are stateful; if the defining query changes, new data will be processed based on the new query and existing data is not recomputed.
2. Dynamic Tables in Flink
* Dynamic Tables: Intro and Definitions [[Link](https://nightlies.apache.org/flink/flink-docs-master/docs/dev/table/concepts/dynamic_tables/)]
3. Flink [[zhihu](https://zhuanlan.zhihu.com/p/61661884)]
4. LINVIEW: Incremental View Maintenance for Complex Analytical Queries (SIGMOD'14) [[paper](https://dl.acm.org/doi/pdf/10.1145/2588555.2610519)]
5. How to Do Incremental Processing Correctly [[blog](https://www.alibabacloud.com/blog/how-to-do-incremental-processing-correctly_599159)]
6. Google Dataflow Incremental Table [[doc](https://cloud.google.com/dataform/docs/incremental-tables#process_a_subset_of_rows_in_an_incremental_table)]
7. Spark stateful streaming processing is stuck in StateStoreSave stage! [[blog](https://xinyeah.github.io/Spark-stateful-streaming-processing-is-stuck-in-StateStoreSave-stage/)]
