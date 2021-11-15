- Introduction 

        2. Introduction to Elasticsearch
        3. Overview of the Elastic Stack
        4. Walkthrough of common architectures
        5. Guidelines for the course Q&A

- Getting Started 

        6. Overview of installation options
        7. Running Elasticsearch & Kibana in Elastic Cloud
        8. Installing Elasticsearch on macOS and Linux
        9. Installing Elasticsearch on Windows
        10. Exploring the Elasticsearch directory
        11. Installing Kibana on macOS and Linux
        12. Installing Kibana on Windows
        13. Understanding the basic architecture
        14. Inspecting the cluster
        15. Sending queries with cURL
        16. Sharding and scalability
        18. Adding more nodes to the cluster (for development)
        19. Overview of node roles
        20. Wrap up

- Managing Documents

        21. Creating & deleting indices
        22. Indexing documents
        23. Retrieving documents by ID
        24. Updating documents
        25. Scripted updates
        26. Upserts
        27. Replacing documents
        28. Deleting documents
        29. Understanding routing
        30. How Elasticsearch reads data
        31. How Elasticsearch writes data
        32. Understanding document versioning
        33. Optimistic concurrency control
        34. Update by query
        35. Delete by query
        36. Batch processing
        37. Importing data with cURL
        38. Wrap up

- Mapping and Analysis

        39. Introduction to this section
        40. Introduction to analysis
        41. Using the Analyze API
        42. Understanding inverted indices
        43. Introduction to mapping
        44. Overview of data types
        45. How the "keyword" data type works
        46. Understanding type coercion
        47. Understanding arrays
        48. Adding explicit mappings
        49. Retrieving mappings
        50. Using dot notation in field names
        51. Adding mappings to existing indices
        52. How dates work in Elasticsearch
        53. How missing fields are handled
        54. Overview of mapping parameters
        55. Updating existing mappings
        56. Reindexing documents with the Reindex API
        57. Defining field aliases
        58. Multi-field mappings
        59. Index templates
        60. Introduction to the Elastic Common Schema (ECS)
        61. Introduction to dynamic mapping
        62. Combining explicit and dynamic mapping
        63. Configuring dynamic mapping
        64. Dynamic templates
        65. Mapping recommendations
        66. Stemming & stop words
        67. Analyzers and search queries
        68. Built-in analyzers
        69. Creating custom analyzers
        70. Adding analyzers to existing indices
        71. Updating analyzers
        72. Wrap up

- Intro to Searching 

        73. A word on document types
        74. Search methods
        75. Searching with the request URI
        76. Introducing the Query DSL
        77. How searching works
        78. Understanding query results
        79. Understanding relevance scores
        80. Debugging unexpected search results
        81. Query contexts
        82. Full text queries vs term level queries

- Term Level Queries 

        83. Introduction to term level queries
        84. Searching for a term
        85. Searching for multiple terms
        86. Retrieving documents based on IDs
        87. Matching documents with range values
        88. Working with relative dates (date math)
        89. Matching documents with non-null values
        90. Matching based on prefixes
        91. Searching with wildcards
        92. Searching with regular expressions

- Full Text Queries 

        93. Introduction to full text queries
        94. Flexible matching with the match query
        95. Matching phrases
        96. Searching multiple fields


- adding boolean logic to queries

        97. Introduction to compound queries
        98. Querying with boolean logic
        99. Debugging bool queries with named queries
        100. How the “match” query works

- Joining queries

        101. Introduction to this section
        102. Querying nested objects
        103. Nested inner hits
        104. Mapping document relationships
        105. Adding documents
        106. Querying by parent ID
        107. Querying child documents by parent
        108. Querying parent by child documents
        109. Multi-level relations
        110. Parent/child inner hits
        111. Terms lookup mechanism
        112. Join limitations
        113. Join field performance considerations

- Controlling  query results

        114. Specifying the result format
        115. Source filtering
        116. Specifying the result size
        117. Specifying an offset
        118. Pagination
        119. Sorting results
        120. Sorting by multi-value fields
        121. Filters

- Aggregations

        122. Introduction to aggregations
        123. Metric aggregations
        124. Introduction to bucket aggregations
        125. Document counts are approximate
        126. Nested aggregations
        127. Filtering out documents
        128. Defining bucket rules with filters
        129. Range aggregations
        130. Histograms
        131. Global aggregation
        132. Missing field values
        133. Aggregating nested objects

- Improving search results 

        134. Introduction to this section
        135. Proximity searches
        136. Affecting relevance scoring with proximity
        137. Fuzzy match query (handling typos)
        138. Fuzzy query
        139. Adding synonyms
        140. Adding synonyms from file
        141. Highlighting matches in fields
        142. Stemming

