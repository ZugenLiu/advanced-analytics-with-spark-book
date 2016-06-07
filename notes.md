# Notes
- Historically, exploratory analytics typically occurs in languages like R, and when it comes time to build production
applications, the data pipelines are rewritten entirely in Java or C++.
- Of course, everybody could save time if the original modeling code could be actually used in the app for which it is written, but languages like R are slow and lack integration with most planes of the production infrastructure stack, and languages like Java and C++ are just poor tools for exploratory analytics. They lack **Read-Evaluate-Print
Loop (REPL)** environments for playing with data interactively and require large amounts of code to express simple transformations. A framework that makes modeling easy but is also a good fit for production systems is a huge win.
- Spark maintains MapReduce’s linear scalability and fault tolerance, but extends it in three important ways. 
  - First, rather than relying on a rigid map-then-reduce format, its engine can execute a more general directed acyclic graph (DAG) of operators. This means that, in situations where MapReduce must write out intermediate results to the distributed filesystem, Spark can pass them directly to the next step in the pipeline.
  - Second, it complements this capability with a rich set of transformations that enable users to express computation more naturally. It has a strong developer focus and streamlined API that can represent complex pipelines in a few lines of code.
  - Third, Spark extends its predecessors with in-memory processing. Its Resilient Distributed Dataset (RDD) abstraction enables developers to materialize any point in a processing pipeline into memory across the cluster, meaning that future steps that want to deal with the same data set need not recompute it or reload it from disk. This capability opens up use cases that distributed processing engines could not previously approach. 
- Spark is well suited for highly iterative algorithms that require 
  - **multiple passes over a data set**, as well as 
  - **reactive applications** that quickly respond to user queries by scanning large in-memory data sets.
- Spark spans the gap between systems designed for exploratory analytics and systems designed for operational analytics.

