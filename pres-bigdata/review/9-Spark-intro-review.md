from opened pptx, write me a short summary on 1 line for each slides

1. **Spark Introduction**: title slide.
2. **Spark history**: timeline from Google's MapReduce (2002–2004) through Hadoop, Spark (2010) and Kubernetes (2015) to Spark on K8s (2020).
3. **From simple to unified**: the Hadoop ecosystem grew into many specialised, overlapping tools, and Spark unifies them into one simpler, extensible engine.
4. **Spark as a unified engine**: a diagram showing Spark as one engine for batch, SQL, streaming and ML workloads.
5. **Multi-purpose, multi-language**: Spark supports Java, Scala, Python and R, plus many data sources.
6. **Spark-Core and its ecosystem**: Core with its data source connectors, cluster managers, language support and modules (SQL, MLlib, GraphX, Streaming).
7. **Getting started**: download Spark, unzip it and add it to PATH, then launch spark-shell, spark-submit or spark-sql.
8. **Scala shell**: launching spark-shell and typing Scala code, including `println("Hello spark")`.
9. **spark-shell usage**: Ctrl-D to exit and `:paste` for multi-line code, with screenshots.
10. **Creating a Dataset**: `spark.createDataset(...)` in the shell, with example output.
11. **Reading a text file**: `spark.read.textFile(...)` on a lorem ipsum file, then `count` returns 4 lines.
12. **Showing a Dataset**: `dataset.show()` and its default parameters (20 rows, truncate=true).
13. **Word count with flatMap**: splitting lines into words with `flatMap` and counting them (69 words).
14. **Running word count locally**: `local[*]` mode and debugging the Java program in an IDE.
15. **spark-submit**: submitting a packaged jar with `--class MainClass JarFile`, with a skipped-log example.
16. **dataset.map**: applies a function to each element, shown alongside the equivalent imperative loop.
17. **dataset.flatMap**: each input can yield many outputs, shown alongside the equivalent imperative loop.
18. **Logical dataset vs physical data**: a Dataset is a logical view of partitions held on executors, with the driver and executor JVMs shown.
19. **Driver vs executors**: the driver runs main(), while executors run the functions on the data and exchange data during shuffles.
20. **Driver API vs executor engine**: contrasts the code logic (driver) with the data and CPU work (executors).
21. **Shuffle and exchange**: repartition, coalesce and wide transformations move data between executors.
22. **Wide vs narrow transformations**: narrow ones stay within a partition, while wide ones require network exchange between executors.
23. **Execution plans**: `repartition().flatMap().explain()` output showing the Exchange step in the physical plan.
24. **Common questions**: a list of open questions on RDD vs Dataset vs DataFrame, drivers, executors, deployment modes and performance.


review all slides for typo, pixels unalignments

