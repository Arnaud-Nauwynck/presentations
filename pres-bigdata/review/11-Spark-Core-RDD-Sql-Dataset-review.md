
11-Spark-Core-RDD-Sql-Dataset.pdf

Based on slide titles (the body text wasn't read):

1. Title: Spark Core RDD and Spark SQL Dataset/DataFrame overview.
2. Outline of the presentation.
3. Launching `./bin/spark-shell` as the entry point.
4. Two built-in variables in the shell: `sc` and `spark`.
5. `sc` (SparkContext, spark-core) vs `spark` (SparkSession, spark-sql).
6. `sc.parallelize(..)` vs `spark.createDataset(..)`: which to use.
7. Spark-core and spark-sql as Maven modules.
8. Key `pom.xml` dependencies.
9. Creating SparkConf, JavaSparkContext and SparkSession in Java.
10. SparkContext is a singleton; SparkSession can be many, with one active.
11. Using the Java and Scala APIs on Dataset and RDD.
12. Java lambdas with Spark need casts due to ambiguous overloads.
13. Java API needs an explicit Encoder, which Scala provides implicitly.
14. The Java API is less convenient than the Scala API.
15. Using `scala.Function1` and inner classes causes NotSerializableException.
16. Fix: use an isolated top-level class that implements Serializable.
17. Debugging Spark with `local[*]` from the IDE.
18. Advanced SQL and Dataset usage.
19. Word count example: "Hello world of BigData".
20. `Dataset.show` defaults: 20 rows, truncate=true.
21. Word count using `flatMap(...).count`.
22. Word count with Spark-core RDD.
23. Word count with RDD: you will rarely use RDD directly.
24. How RDD and Dataset look similar, and where they differ.
25. Dataset vs RDD comparison.
26. What Datasets and RDDs are, and how they work.
27. What an RDD is.
28. Details of the RDD class.
29. Where to find the Spark source code on GitHub.
30. RDD javadoc (1/3).
31. RDD javadoc (2/3).
32. RDD javadoc (3/3).
33. The RDD research paper.
34. RDD abstract methods.
35. Abstract `org.apache.spark.rdd.RDD` class signature.
36. RDD class overview.
37. RDD operators.
38. Sub-class hierarchy extending RDD. *(hidden)*
39. Abstract RDD class with many concrete sub-classes. *(hidden)*
40. One algorithm or transformation maps to one RDD sub-class.
41. Calling a transform function creates a new linked RDD.
42. Calling `compute()` runs `dependency.compute()`.
43. RDD dependencies form a DAG (directed acyclic graph).
44. Three equivalent formalisms: SSA-style API, expression algebra, DAG.
45. Fault-tolerant computation. *(hidden)*
46. Coarse-grained scheduler and executor. *(hidden)*
47. What a Dataset is.
48. Dataset is a SQL wrapper around RDD, in spark-sql.
49. Dataset source documentation.
50. Dataset class javadoc (1/4).
51. Dataset javadoc (2/4).
52. Transformations produce new immutable Datasets, with no update method.
53. Dataset operations overview.
54. Dataset javadoc (3/4).
55. Internals of Dataset.
56. Dataset javadoc (4/4).
57. The `Encoder<T>` class.
58. Spark type system and DataTypes.
59. Internal Spark type system.
60. Spark DataType details.
61. Hive compatibility: Spark SQL supports struct, list and map.
62. Logical plan, physical plan and expression classes.
63. Encoder as an internal expression with a DataType.
64. Expression classes.
65. `Dataset<T>`, and DataFrame as `Dataset<Row>`.
66. The deprecated DataFrame API, now `Dataset<Row>`.
67. The `org.apache.spark.sql.Row` interface.
68. `Row` class methods: whether you need to care.
69. SQL vs compiled custom classes.
70. SQL `where` vs `filter(lambda predicate)`.
71. Concise code vs maintainable code.
72. Spark Tungsten: internal memory encoding for Row.