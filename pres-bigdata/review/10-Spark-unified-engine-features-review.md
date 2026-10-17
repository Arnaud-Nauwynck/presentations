from opened pptx, write me a short summary on 1 line for each slides

Deck: `C:\arn\devPerso\Presentations\pres-bigdata\10-Spark-unified-engine-features.pptx` (101 slides)

1. Title: Spark Unified Engine Features (SQL, Dataset & API)
2. Outline
3. Reminder: Spark RAW to LAKE samples
4. Typical usage: processing RAW to LAKE
5. Typical RAW to LAKE as Spark Java code
6. Typical RAW to LAKE processing as Spark SQL
7. Example of LAKE aggregation
8. Example of "latest value" query using over(partition by)
9. Step-by-step explained
10. Typical RAW to LAKE as Spark Java code (detailed)
11. RAW to LAKE step 1/4: read to Dataset
12. RAW to LAKE step 2/4: transform Dataset
13. RAW to LAKE step 3/4: repartition Dataset
14. RAW to LAKE step 4/4: write Dataset
15. How it works?
16. Zooming in
17. RAW to LAKE step 1/4: read to Dataset (detailed)
18. Analogy: playing music with N musicians and no conductor vs an orchestra
19. Reading N files: assigning tasks to executors
20. Parallelism remark 1/2: one file gives only one task
21. Parallelism remark 2/2: splittable formats (Parquet) read like a directory
22. Zooming in on RAW to LAKE step 2/4: transform Dataset
23. WholeStageCodegen
24. Advanced transform: Row → Java → map() → Java → Row
25. Explaining as().map().toDF()
26. Converting tabular SQL Row to Java beans
27. RAW to LAKE step 3/4: repartition Dataset (detailed)
28. Example: repartition(N).map(…).repartition(1)
29. Example transformation in SQL
30. Typical RAW to LAKE as Spark SQL
31. Explained: SQL (→ files) → Dataset
32. Hive MetaStore
33. Location directory and partitions
34. Dataset → INSERT into SQL table (→ files)
35. More Java ↔ SQL interactions
36. Executing a single SQL statement from Java
37. Running `spark-sql.sh -f sql-script.hql`
38. HQL: Hive Query Language, a `;`-separated sequence of DML and DDL statements
39. spark-sql.sh is equivalent to custom Spark code plus SQL escape parsing
40. Java Dataset as a SQL view
41. Calling Java from SQL: user-defined functions
42. Spark as a unified SQL, files and Java platform
43. Spark as a unified engine (distributed storage and compute)
44. Dataset API and SQL extensions
45. More extensions: Hadoop FileSystem API
46. More extensions: cluster scheduler API
47. Picture slide: Apache Spark core concepts, architecture and internals (no title)
48. More extensions: backporting the API to Python and R
49. Spark Core
50. RDD principles: low-level internal SPI, not for direct use
51. RDD[T]: Resilient Distributed Dataset of T
52. RDD doc (1/3)
53. RDD abstract methods
54. RDD doc (2/3)
55. RDD doc (3/3)
56. RDD paper
57. Fault tolerance: computation
58. Hidden: what happens if a Spark executor crashes or a node stops?
59. CoarseGrain scheduler/executor
60. RDD: Resilient Distributed Dataset
61. Dataset: collection of objects, one CPU per partition
62. Distribution: partition → executor → node
63. Optimizing parallelism: adapt partitions to the number of cores
64. Skewed data: needs equal repartitioning
65. Narrow vs wide transformations
66. Dataset
67. Dataset = (roughly RDD) set of data plus an encoder
68. Dataset = SQL wrapper for RDD, in the spark-sql module
69. spark-sql module: SQL grammar parsed to code and expression AST
70. Encoder: internal expression with data type
71. class Dataset<T> internals
72. Encoder<T>
73. Types: nested struct/map/array and SQL lateral view
74. Internal Spark type system
75. Spark DataType
76. Hive and Spark SQL support struct, list and map
77. Nested fields in Parquet, ORC and JSON formats
78. Nested fields in Spark SQL UDFs
79. SQL grammar extension: lateral view
80. More SQL: collect_list(row) → List
81. UDF / UDAF (user-defined aggregate function)
82. List, map and struct: denormalize data to avoid joins
83. Data transformations, lineage and DAG (directed acyclic graph)
84. Abstract RDD class → many concrete subclasses
85. One algorithm/transformation → one RDD subclass
86. Calling a transform function creates a new linked RDD
87. Calling compute() → dependency.compute()
88. Dataset transformations API (similar to RDD methods)
89. Dependencies: the DAG
90. Three equivalent formalisms: SSA create API, expression algebra, DAG
91. Dataset operations
92. Dataset transformation != action: transformations are lazy and return a Dataset, actions run immediately and return a value to the driver (no title)
93. Avoiding repeated Dataset recomputation (RAM + disk vs CPU trade-off)
94. Spark Streaming: micro-batches
95. Spark DStream API as an enriched Dataset API
96. DStream usage similar to the Dataset API
97. Typical usage: streaming vs daily batch
98. Typical architectures: Lambda vs Kappa
99. Takeaway: what did you learn?
100. Spark Core
101. MindMap


on opened deckcraft, review all slides for typos

I reviewed all 101 slides and found these typos. Slide numbers are 1-based, as shown in the deck. I have not changed anything yet.

**Spelling / wording**
- Slide 8: "cristalisation" → "crystallisation"
- Slide 14: `.fomat(` → `.format(`
- Slide 14: `hdfs://lake/trig/domain/table`, likely "team" (other paths use "team")
- Slide 21: "256 Mo" → "256 MB"
- Slide 28: "INNEFFICIENT" → "INEFFICIENT"
- Slide 32: "metadatas" → "metadata"
- Slide 44: "Lamba" → "Lambda"
- Slide 45: "Spark rely on API" → "Spark relies on the API"
- Slide 48: "Langages" → "Languages"
- Slide 49: "Langages Support" → "Languages Support"
- Slide 59: "Executer" → "Executor"
- Slide 62: "per nodes" → "per node"
- Slide 63: "parralelism" → "parallelism"
- Slide 64: "need Repartitioned equally" → "need to be repartitioned equally"
- Slides 69, 70: "Syntaxic" → "Syntactic"
- Slide 71: `shema()` → `schema()`
- Slide 77: "definiton" → "definition"
- Slides 70, 74, 75, 80: "Annexe" (French) → "Appendix"
- Slide 95: "Dstream" → "DStream"; "RealTime" → "Real-Time"
- Slide 96: "DStream using similar to Dataset API" is missing a verb (likely "is")
- Slide 99: "Take Away What Did you learn ?" → "Takeaway: What did you learn?"
- Slide 101: "Langages Support" → "Languages Support"

**Code in slides**
- Slides 5, 10: `.as(Encoder.bean(Bean.Class)` is missing a closing `)`
- Slide 6, 30, 32: curly quotes (‘ ’) inside SQL strings
- Slide 38: stray `\"` in `"select ... from Table2\"`
- Slide 41: mismatched quotes in `« udf_func1",`
- Slide 80: `FROM ( SELECT employee` → likely `SELECT * FROM employee`
- Slide 101: `/+REPARTITION(3, col1) */` → `/*+ REPARTITION(3, col1) */`
- Slide 101: `sortWithinPartitions` differs from `sortWithinPartition` used elsewhere

**Factual / consistency (not strictly typos)**
- Slide 90: "SSA = Single State Assignments" → "Static Single Assignment"
- "Api" vs "API" and "Sql" vs "SQL" are used inconsistently across slides (for example slides 1, 90)

Some text in the deck looks like run-together words (for example "Explanationstep-by-step"). I treated those as extraction artifacts, because the inspected slide text has proper spacing.

Should I apply the fixes to the open deck? If so, I'll correct the clear typos and leave the wording and factual items for you to decide.