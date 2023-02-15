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
5. Differential Datalog (DDlog) [[website](https://research.vmware.com/projects/differential-datalog-ddlog)][[github](https://github.com/vmware/differential-datalog)]👉 (Liz, Sherry)
> DDlog is a programming language for incremental computation, for writing programs that continuously update their output in response to changes.
6. What’s inside Materialize? An architecture overview [[blog](https://materialize.com/blog/architecture/#differential-dataflow)]



### Dataflow Model
 > (Databricks) Structured Streaming adopts the definitions of event time, processing time, watermarks and triggers from __Dataflow__ but incorporates them in an incremental model.

 > There were two main reasons for Flink’s rise to prominence:
  Its rapid adoption of the __Dataflow__/Beam programming model, which put it in the position of being the most semantically capable fully open source streaming system on   the planet at the time.

1. The Dataflow Model: A Practical Approach to Balancing Correctness, Latency, and Cost in Massive-Scale, Unbounded, Out-of-Order Data Processing [[paper](https://static.googleusercontent.com/media/research.google.com/zh-CN//pubs/archive/43864.pdf)] [[zhihu](https://zhuanlan.zhihu.com/p/54739130)]
2. Structured Streaming: A Declarative API for Real-Time Applications in Apache Spark [[paper](https://dl.acm.org/doi/pdf/10.1145/3183713.3190664)] [[jira](https://issues.apache.org/jira/browse/SPARK-20928)] [[doc](https://spark.apache.org/docs/latest/structured-streaming-programming-guide.html)] [[zhihu](https://zhuanlan.zhihu.com/p/51883927)] [[blog](https://developer.aliyun.com/article/690913) compare with Spark Streaming]
> Structured Streaming automatically incrementalizes queries on static datasets expressed through Spark’s SQL and DataFrame APIs [8], meaning that users typically only need to understand Spark’s batch APIs to write a streaming query. Event time concepts are especially easy to express and understand in this model.
 

### Temporal Query Model
1. Trill: A High-Performance Incremental Query Processor for Diverse Analytics (VLDB'14) [[paper](http://www.vldb.org/pvldb/vol8/p401-chandramouli.pdf)]

## 🔥 OLVM (online view maintainance) 👉 (quick go-through)
1. incremental recomputation of active relational expressions (TKDE'91) [[paper](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=91063)]
2. Incremental Maintenance of Views with Duplicates (SIGMOD' 95) [[paper](https://homepages.inf.ed.ac.uk/libkin/papers/sigmod95.pdf)]
3. Incremental Maintenance for Analytics [[website](https://fdbresearch.github.io/ivm.html)]
4. Mathematical principles in RisingWave (Delta Join) [[website](https://www.risingwave-labs.com/blog/shared-indexes-and-joins-in-streaming-databases/)] [[website 2](https://www.skyzh.dev/posts/articles/2022-05-29-shared-state-in-risingwave/)]

### PostgreSQL IVM (incremental view maintenance) [[wiki](https://wiki.postgresql.org/wiki/Incremental_View_Maintenance#Restrictions_on_view_definition)]
1. pgcon 2020: The Way for Updating Materialized Views Rapidly [[pdf](https://www.pgcon.org/events/pgcon_2020/sessions/session/56/slides/47/pgcon2020_nagata_the_way_to_update_materialized_views_rapidly.pdf)]
2. pgcon eu 2018: Implementing Incremental View Maintenance on PostgreSQL [[pdf](https://www.postgresql.eu/events/pgconfeu2018/sessions/session/2195/slides/144/Implementing%20Incremental%20View%20Maintenance%20on%20PostgreSQL%20.pdf)]
3. IVM discussion [[kick-off](https://www.postgresql.org/message-id/20181227215726.4d166b4874f8983a641123f5@sraoss.co.jp)] [[proposal in JP](https://ipsj.ixsq.nii.ac.jp/ej/?action=pages_view_main&active_action=repository_view_main_item_detail&item_id=191222&item_no=1&page_id=13&block_id=8)]
4. IVM testing on TPC-H and TPC-DS [[from Russia](https://postgrespro.ru/list/thread-id/2419111)]
5. Utilizing IDs to Accelerate Incremental View Maintenance (SIGMOD'15) [[paper](https://dl.acm.org/doi/10.1145/2723372.2750546)]
6. Maintaining views incrementally (SIGMOD'93) [[paper](https://dl.acm.org/doi/10.1145/170035.170066)]


## 🔥 States Management
1. Delta Joins and Late Materialization: Understand how to optimize joins with indexes and late materialization [[blog](https://materialize.com/blog/delta-joins/)]
2. What consistency guarantees should you expect from your streaming data platform? [[blog](https://materialize.com/blog/consistency/)]
> In-order reliable message delivery is not enough. Showing views over streams of data requires thinking through additional consistency semantics to deliver correct results.
3. Databricks: Delta Live Table [[blog](https://blogs.perficient.com/2022/07/11/top-5-take-aways-from-databricks-data-ai-summit-2022/)][[youtube](https://www.youtube.com/watch?v=zo6K6g2jfqY)]
> Announcing __Enzyme__, a new optimization layer designed specifically to speed up the process of doing ETL – Transforming data to prepare it for downstream analysis is a prerequisite for most other workloads on the Databricks platform. While SQL and Data frames make it relatively easy for users to express their transformations, the input data constantly changes. This requires re-computation of the tables produced by ETL. Enzyme is a a new optimization layer for ETL. Enzyme efficiently keeps up to date a materialization of the results of a given query stored in a Delta table. It uses a cost model to choose between various techniques, including techniques used in traditional materialized views, delta-to-delta streaming, and manual ETL patterns commonly used by data engineers.
4. Shared Arrangements: practical inter-query sharing for streaming dataflows (VLDB' 20) [[paper](https://people.csail.mit.edu/malte/pub/drafts/2019-kpg.pdf)] 👉(Liz, Sherry)
5. Noria: dynamic, partially-stateful data-flow for high-performance web applications (OSDI' 18) [[paper](https://www.usenix.org/conference/osdi18/presentation/gjengset)] [[github](https://github.com/mit-pdos/noria)] [[presentation](https://www.youtube.com/watch?v=kVv9Pik6QGY)] [[discussion](https://corecursive.com/030-rethinking-databases-with-jon-gjengset/)]👉 (Rui, Sherry)

## 🔥🔥 Pipeline management and Serverless
1. Multiple-Query Optimization [[paper](http://daslab.seas.harvard.edu/reading-group/papers/mqo.pdf)] 👉 (Liz)
2. Resource Allocation in Serverless Query Processing [[paper](https://arxiv.org/pdf/2208.09519.pdf)]

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
> Linear Algebra
5. How to Do Incremental Processing Correctly [[blog](https://www.alibabacloud.com/blog/how-to-do-incremental-processing-correctly_599159)]
6. Google Dataflow Incremental Table [[doc](https://cloud.google.com/dataform/docs/incremental-tables#process_a_subset_of_rows_in_an_incremental_table)]
7. Spark stateful streaming processing is stuck in StateStoreSave stage! [[blog](https://xinyeah.github.io/Spark-stateful-streaming-processing-is-stuck-in-StateStoreSave-stage/)]

## Machine/Deep Learning with Incremental Computation on Structured Data

### **Part 1** Paper List / Preliminary
1. Best-Incremental-Learning [[GitHub Repo](https://github.com/Vision-Intelligence-and-Robots-Group/Best-Incremental-Learning)]
2. Awesome-Incremental-Learning [[GitHub Repo](https://github.com/xialeiliu/Awesome-Incremental-Learning)]
3. Continual learning: A comparative study on how to defy forgetting in classification tasks. [[PDF](https://www.researchgate.net/publication/335908453_Continual_learning_A_comparative_study_on_how_to_defy_forgetting_in_classification_tasks)]

### **Part 2** Traditional Machine Learning (e.g., Decision Tree, SVM)
#### **Part 2.1** w/ Incremental Computation
1. An Introduction to Online Machine Learning [[Blog](https://medium.com/danny-butvinik/https-medium-com-dannybutvinik-online-machine-learning-842b1e999880)]
2. Incremental online machine learing [[Blog](https://medium.com/analytics-vidhya/incremental-online-learning-9868861db880)]
3. Incremental on-line learning: A review and comparison of state of the art algorithms (Neurocomputing 2018) [[PDF](https://pdf.sciencedirectassets.com/271597/1-s2.0-S0925231217X00489/1-s2.0-S0925231217315928/main.pdf?X-Amz-Security-Token=IQoJb3JpZ2luX2VjEHUaCXVzLWVhc3QtMSJHMEUCIQCM1%2FOHhUHvUX5d2jey%2B6AFBW1nJdfLYzl43g5fI4%2B%2BOwIgS3wwXxWyI0ToJwaXhd%2Bf%2BwBXdFDWBI5uXIxv%2Fn%2FqkVAq1QQI%2Fv%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FARAFGgwwNTkwMDM1NDY4NjUiDP1qwRWYzyDyxxKUIyqpBHFfrFl86OqF%2Ff2UWaTdJOPpCJD3wQacl0HZmK6TXYE%2BiH%2Bx2eLwGozSFO1BqHeImX%2Bx3V8Jo9fdZyf8%2B%2BP7Vtelq4y88ov6%2FEX5Rqq5Dnhc6UIqhOamF6WRV3FG9Dky5QZf9frMs%2FCGo3gT3EMD%2Faw%2FH8ibinfxh3SaFo%2B7yzPhmR6eWFgnCRBfEYRTod0A%2BcmRTzZDegcTlPa5J%2FTDE6MiM%2BWal8Cs7pKsQ%2FhfXktSLA8dsUX0WKkGKU1b%2FGulONo%2BW7%2FkOwPBpuk9S6yq%2FukJo1z1iMyDhPJdeLE5f6BjAQ3gxzkovQNjbFLJPBv9EjGyFEsID8wJ8H9dP0cruFsGvP4emkAJcRyGcc%2BTdBPWKW04za64qj54hvUN%2BFhJpWQVNSKNXD%2F61DOEr90Fzl4NDg%2Fs06W45VL3FydOsoR%2F3v6poWYD%2FDTX6lzQP3d0pyW1BC%2Fvxp54bfsHzsMnAIDUfvwtr4geKnBCRbRNzfnpsUTNKRJHif5rArnz2iASfH3kh1pbqzrdpDarc%2Fi%2B6aqvrElSLz6iLUfFvslxjGQVmQUrRhn13b1zTga6lmHsI6oSKUIuoFxLrGxu615dyhBRYXRWkyIhJA5U9AJMvVWQYKVlSpcJvCMELPBXrYPTAW6spRwgv6rXm%2B2MjVTBTD4nWA%2BkqRhXCPWOHbjG6AayiZNWwSPKrxImpNFDUCMHIjln%2FVordllUYS8D%2Bwfo2d4%2BOiuMMgY%2FuEgw4pisnwY6qQFg2IflojxhX7i7VljaDReh%2FQ9KH8DC3XqG2PsDJzVeT6IhbMK%2Fgx4veSWnCKyAx5GGBaM9zJqvvJbP%2FgQ5BBnjZMhH6MFyGk7KbG3JLn20RYp5ZIG874kS25yJAko7vQAS9fY0hX3ARkzskhBbYm0nUO3dxm%2BY7roSt0GCXYN%2BzDQPk440rnpW0Ve4WM9242xbEwTbKtMr3QunorkPqVnrTqd4hPu1%2F4cB&X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Date=20230214T052635Z&X-Amz-SignedHeaders=host&X-Amz-Expires=300&X-Amz-Credential=ASIAQ3PHCVTY34HXUUS6%2F20230214%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Signature=b297510a625eff899f4f49cc358ce0f518d46643f9e0235ba8b655595bee72c2&hash=efd0e5071ec1b39e6fb0fd9db76d8dd74ce5c845d87a6261e469f6b66bdd4aa1&host=68042c943591013ac2b2430a89b270f6af2c76d8dfd086a07176afe7c76c2c61&pii=S0925231217315928&tid=spdf-7f665975-f6ba-46bd-b083-b532de9a51ab&sid=453bbbb493a3c5477c2b4fa480c88d6b394bgxrqa&type=client&tsoh=d3d3LnNjaWVuY2VkaXJlY3QuY29t&ua=060e585f575d595607&rr=799363c8dd170990&cc=hk)]
4. Progress In Incremental Machine Learning (NIPS 2002 Workshop) [[PDF](https://citeseerx.ist.psu.edu/document?repid=rep1&type=pdf&doi=289ba69f2f9d6993bdb512d9784f03918a82baf2)]
5. Incremental Support Vector Learning: Analysis, Implementation and Applications (JMLR 2006)[[PDF](https://www.jmlr.org/papers/volume7/laskov06a/laskov06a.pdf)]
6. Mondrian Forest: Efficient Online Random Forests (NIPS 2014) [[PDF](https://proceedings.neurips.cc/paper/2014/file/d1dc3a8270a6f9394f88847d7f0050cf-Paper.pdf)]

#### **Part 2.2** w/ Structured Data
<!-- 1. Markov logic networks (Machine Learning 2006) [[PDF](https://link.springer.com/content/pdf/10.1007/s10994-006-5833-1.pdf)]
2. Relational Dependency Networks (JMLR 2007) [[PDF](https://scholarworks.umass.edu/cgi/viewcontent.cgi?article=1125&context=cs_faculty_pubs)] -->
1. Structured Machine Learning: The Next Ten Years (Machine Learning 2008) [[PDF](https://link.springer.com/article/10.1007/s10994-008-5079-1)]
2. Tabular Data: Deep Learning is not all you need (Information Fusion 2022) [[PDF](https://arxiv.org/pdf/2106.03253.pdf?trk=public_post_comment-text)]

#### 💥 **Part 2.3** w/ Incremental Computation on Structured Data
- I do not find papers that focus on this specific topic. I think this part is more related to incremental computation/learning since structured data can always be preprocessed (how to retain the internal relations among the data is crucial) and then fed into the traditional machine learning models.

### **Part 3** Deep Learning (e.g., DNNs)
#### **Part 3.1** w/ Incremental Computation
1. Learn++: An Incremental Learning Algorithm for Supervised Neural Networks (Transactions on System 2001) [[PDF](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=983933)]
2. End-to-End Incremental Learning (ECCV 2018) [[PDF](https://openaccess.thecvf.com/content_ECCV_2018/papers/Francisco_M._Castro_End-to-End_Incremental_Learning_ECCV_2018_paper.pdf)]
3. Rectification-based Knowledge Retention for Continual Learning (CVPR 2021) [[PDF](https://openaccess.thecvf.com/content/CVPR2021/papers/Singh_Rectification-Based_Knowledge_Retention_for_Continual_Learning_CVPR_2021_paper.pdf)]
4. DER: Dynamically Expandable Representation for Class Incremental Learning (CVPR 2021) [[PDF](https://scholar.google.com/scholar_url?url=http://openaccess.thecvf.com/content/CVPR2021/papers/Yan_DER_Dynamically_Expandable_Representation_for_Class_Incremental_Learning_CVPR_2021_paper.pdf&hl=en&sa=T&oi=gsb-gga&ct=res&cd=0&d=15603649429564073640&ei=gCfrY8bGC4jQmQHDkoS4BA&scisig=AAGBfm1QbvL-VEh-sOE1K5MlnQOEdWsWFA)]

#### **Part 3.2** w/ Structured Data
1. How to use deep learning to deal with structured data [[Blog](https://www.jiqizhixin.com/articles/2017-12-04-7)]
2. AI Should not Leave Structured Data Behind [[Blog](https://towardsdatascience.com/ai-should-not-leave-structured-data-behind-33474f9cd07a)]
3. Deep Learning with Structured Data [[Book](https://livebook.manning.com/book/deep-learning-with-structured-data/chapter-1/29)]
4. Revisiting Deep Learning Models for Tabular Data (NIPS 2021) [[PDF](https://proceedings.neurips.cc/paper/2021/hash/9d86d83f925f2149e9edb0ac3b49229c-Abstract.html)]
5. TabNet: Attentive Interpretable Tabular Learning (AAAI 2021) [[PDF](https://ojs.aaai.org/index.php/AAAI/article/view/16826)]
4. Deep Neural Networks and Tabular Data: A survey (TNNLS 2022) [[PDF](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=9998482)]

#### 💥 **Part 3.3** w/ Incremental Computation on Structed Data
- I do not find papers that focus on this specific topic for DL either. I think the reasons are similar to that listed in **Part 2.3**.

### **Part 4** Tools or Implementations
1. Machine learning and deep learning on tabular data [[ArcGIS](https://developers.arcgis.com/python/guide/ml-and-dl-on-tabular-data/)]
2. Incremental learning [[sklearn](https://scikit-learn.org/0.15/modules/scaling_strategies.html#incremental-learning)]
2. Machine Learning with Tabular Data [[Google Cloud](https://cloud.google.com/vertex-ai/docs/tabular-data/tabular101)]
