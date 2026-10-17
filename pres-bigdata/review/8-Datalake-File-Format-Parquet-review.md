

> from opened pptx, write me a short summary on 1 line for each slides

  Called deckcraft 2 times

The open deck is 8-Datalake-File-Format-Parquet.pptx (88 slides). Summaries are based on slide titles, with slide 54 read directly since its title is blank.

1. Title: Datalake File Format: Parquet overview.
2. Outline: Agenda of the presentation.
3. Parquet is a structured format, strongly typed (schema): Parquet stores data with a enforced schema.
4. File Formats: Comparison of the main data file formats.
5. Structured types: struct, array and map nesting in Parquet.
6. Type constraint = Schema: Column types are enforced by the schema.
7. Parquet SDK / Converter / ObjectModel: Java libraries and object model for reading and writing Parquet.
8. Parquet separates data and metadata: Metadata is kept apart from the data pages.
9. Parquet schema in metadata footer: The schema is stored in the file footer.
10. Parquet for small files?: Why small Parquet files are inefficient.
11. Read Parquet footer only: Reading just the footer to get schema and layout cheaply.
12. Why footer instead of header?: Rationale for storing metadata at the end of the file.
13. Parquet is columnar: Data is stored column by column rather than row by row.
14. Parquet columnar file format: Visual of the columnar layout.
15. Columnar: memory alignment and vectorized CPU: Column layout enables vectorized processing.
16. Vectorized code: Fewer branches, loops and calls per value.
17. Column pruning optimization: Only the needed columns are read.
18. IO reads compared with JSON, CSV, Avro: Read volume comparison across formats.
19. Parquet is splittable: Files can be split for parallel reads.
20. Splitting by row groups: Row groups are the unit of splitting.
21. Row group ~ Spark partition ~ executor thread: Mapping from row groups to Spark parallelism.
22. 1 row group → 1 Spark partition by default: Default partitioning behavior.
23. N row groups → up to P Spark partitions: File splits across partitions.
24. Text, CSV, JSON file splits: How row-based text formats are split.
25. CSV example: A 3.2 GB CSV yields 26 splits.
26. Parquet is compressible: Snappy and gzip compression options.
27. *.gz is not splittable: Gzipped files cannot be split.
28. Compression algorithms: Overview of available codecs.
29. PARQUET.{snappy | gz}: Compression choice and its effect on size and speed.
30. Parquet encodings: Overview of encoding techniques.
31. Run-length encoding (RLE): Compresses repeated values.
32. Size of adding a constant column: RLE makes constant columns almost free.
33. Dictionary encoding: Replaces values with dictionary indexes.
34. Dictionary size limit: Dictionary encoding falls back when it grows too large.
35. Delta encoding: Stores differences between consecutive values.
36. Low-level value encoding with Thrift TCompactProtocol: Metadata serialization format.
37. Variable-length integers: Varint encoding for integers.
38. Variable-length encoding for negative numbers: Handling the sign in varints.
39. ZigZag encoding for ints: Converts signed ints to unsigned before varint encoding.
40. Nested structures encoding: Definition and repetition levels for map, struct and list.
41. Record-oriented storage as column paths: Nested records stored as path-based columns.
42. Repetition, definition and value triplets: Complex but efficient nested encoding.
43. Parquet statistics: Min and max values are stored per column.
44. Column statistics per row group: Min/max per row group enables skipping.
45. Reading metadata: Schema, offsets and statistics are read from the footer.
46. Bloom filters: Parquet can use bloom filters for lookups.
47. Bloom filter details: How the filter is built and queried.
48. Predicate push-down: Filters are pushed into the reader.
49. Push-down path from Spark to Parquet to storage: Layers where filters are applied.
50. Statistics to skip row groups: WHERE clauses skip row groups using stats.
51. Column pruning plus row-group pruning: Together they minimize reads.
52. Badly sorted files: Poor sorting gives weak min/max stats and false positives.
53. Write once, read many: Parquet is optimized for this access pattern.
54. Avoid many small files: Use repartition(1) or coalesce(1) to reduce file count, with the code example.
55. When data does not fit in memory: Compromise by repartitioning to a smaller N.
56. Repartition by column: Partitioning output by a column value.
57. Repartition by column with hash count: Partitioning by column with a fixed hash bucket count.
58. sortWithinPartitions: Sorting rows inside each partition before writing.
59. sortWithinPartitions for compact stats: Sorting makes row-group statistics tighter.
60. Dataset.write bucketBy: Another option for bucketed output.
61. Analyzing Parquet files with parquet-cli: Introduces the parquet-cli tool.
62. Analysing Parquet files with parquet-cli: Continued parquet-cli usage.
63. Finding the jar in Maven: Where to search for parquet-cli on Maven Central.
64. Searching for parquet-cli in Maven: Search query for the artifact.
65. Downloading parquet-cli: Use version 1.13.0 to match Spark's jars.
66. Launching parquet-cli: How to run the tool.
67. parquet-cli meta, part 1: Viewing file metadata.
68. parquet-cli meta, part 2: More metadata output.
69. parquet-cli meta piped to grep: Filtering row-group info.
70. parquet-cli column-size: Showing per-column sizes.
71. Column sizes and sorting: Sorting columns by size.
72. Parquet column sizes summary: Summary of column size results.
73. Graphical web UI tools?: Looking for visual tools to inspect Parquet.
74. hyparquet: A JavaScript Parquet parser library.
75. Parquet metadata visualizer: A visualizer tool for Parquet metadata.
76. Parquet metadata visualizer repo: Link to the GitHub project.
77. Parquet metadata viewer: Another metadata viewing tool.
78. Parquet metadata viewer (continued): More on the viewer.
79. RowGroup and ColumnChunk: Structure of row groups and column chunks.
80. ColumnChunk and pages: Structure of pages inside a column chunk.
81. Offset and column indexes: Index structures for skipping data.
82. Recent project (~1 month): A young project welcoming contributions.
83. Vibe-coded project: Built with AI assistants such as Claude and ChatGPT.
84. Work in progress: Current status of the project.
85. Conclusion: Closing summary.
86. Mind map: Visual recap of the topics.
87. Questions?: Q&A slide.



> any remarks/suggestions on slides ?

Based on the titles (I haven't checked body text or rendering):

Typos and wording
- Slide 3: "Strongly Typed (Schema)" reads awkwardly; consider "strongly typed, schema-based".
- Slide 25: "3.2 Go", "~128 Mo" use French units. Use "3.2 GB", "~128 MB".
- Slide 26: "Compressable" → "Compressible".
- Slide 29: "gz" → "gzip" (the Parquet codec name).
- Slides 61/62: "Analyzing" vs "Analysing". Pick one spelling.
- Slide 77/78: "Parquet Metadata Viewer" is duplicated. Merge or retitle.
- Slide 75/76: "Visualizer" in the title, "vizualizer" in the URL.
- Slide 53: blank title. Add one, e.g. "Write once, read many".

Structure
- Slide 82 "A very recent project (~1 month)": time-relative, and it will be stale. Give a date or drop it.
- Slide 83 "Vibe Coding" and slide 84 "Work In Progress": consider merging into the conclusion.
- Slides 13, 28, 86 have 100+ shapes each. Check for overflow or clutter.
- Slide 54 is a code slide with mixed repartition/coalesce advice. Consider a short note on when to use each.

Want me to check body text and render the dense slides?



> any thing else important to add on parquet ?

Yes, these are missing or thin:

- Schema evolution: adding/renaming columns, mergeSchema, and how readers handle mismatched files.
- Table formats: Delta Lake, Apache Iceberg, Hudi sit on top of Parquet and add ACID, time travel and deletes.
- Compression: zstd and lz4 are common alternatives to snappy/gzip. Mention the size vs CPU trade-off.
- Partitioning on disk: Hive-style col=value/ directories for partition pruning, distinct from row-group pruning.
- Sizing: row groups and files around 128 MB to 1 GB. Too small hurts, too large hurts memory.
- Logical types and nulls: timestamps, decimals, strings, and how nulls are stored.
- Encryption: Parquet modular encryption.
- Column index and page index: the deck mentions offset/column indexes, but not the page-level stats.
- Comparison with ORC and Avro: when to pick each. Slide 18 compares IO but not the ecosystem.
- Pitfalls: filter pushdown does not apply to every expression, and the Spark config knobs (spark.sql.parquet.*) are worth listing.


