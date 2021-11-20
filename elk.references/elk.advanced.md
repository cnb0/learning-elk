Section 1: Fundamentals And Core APIs
Overview Of Elasticsearch 7
            Preparing your environment
            Running Elasticsearch
            Basic Elasticsearch configuration
            Important system configuration
            Talking to Elasticsearch
            Using Postman to work with the Elasticsearch REST API
            Elasticsearch architectural overview
            Elastic Stack architecture
            Elasticsearch architecture
            Between the Elasticsearch index and the Lucene index
            Key concepts
            Mapping concepts across SQL and Elasticsearch
            Mapping
            Analyzer
            Standard analyzer
            API conventions
            New features
            New features to be discussed
            New features with description and issue number
            Breaking changes
            Aggregations changes
            Analysis changes
            API changes
            Cluster changes
            Discovery changes
            High-level REST client changes
            Low-level REST client changes
            Indices changes
            Java API changes
            Mapping changes
            ML changes
            Packaging changes
            Search changes
            Query DSL changes
            Settings changes
            Scripting changes
            Migration between versions

Index APIs

            Index management APIs
            Basic CRUD APIs
            Index settings
            Index templates
            Index aliases
            Reindexing with zero downtime
            Grouping multiple indices
            Views on a subset of documents
            Miscellaneous
            Monitoring indices
            Indices stats
            Indices segments, recovery, and share stores
            Index persistence
            Advanced index management APIs
            Split index
            Shrink index
            Rollover index

Document APIs

            The Elasticsearch document life cycle
            What is a document?
            The document life cycle
            Single document management APIs
            Sample documents
            Indexing a document
            Retrieving a document by identifier
            Updating a document
            Removing a document by identifier
            Multi-document management APIs
            Retrieving multiple documents
            Bulk API
            Update by query API
            Delete by query API
            Reindex API
            Copying documents
            Migration from a multiple mapping types index

Mapping APIs

            Dynamic mapping
            Mapping rules
            Dynamic templates
            Meta fields in mapping
            Field datatypes
            Static mapping for the sample document
            Mapping parameters
            Refreshing mapping changes for static mapping
            Typeless APIs working with old custom index types

Anatomy Of An Analyzer

            An analyzer's components
            Character filters
            The html_strip filter
            The mapping filter
            The pattern_replace filter
            Tokenizers
            Token filters
            Built-in analyzers
            Custom analyzers
            Normalizers

Search APIs

            Indexing sample documents
            Search APIs
            URI search
            Request body search
            The sort parameter
            The scroll parameter
            The search_after parameter
            The rescore parameter
            The _name parameter
            The collapse parameter
            The highlighting parameter
            Other search parameters
            Query DSL
            Full text queries
            The match keyword
            The query string keyword
            The intervals keyword
            Term-level queries
            Compound queries
            The script query
            The multi-search API
            Other search-related APIs
            The _explain API
            The _validate API
            The _count API
            The field capabilities API
            Profiler
            Suggesters

Section 2: Data Modeling, Aggregations Framework, Pipeline, And Data Analytics

Modeling Your Data In The Real World

            The Investor Exchange Cloud
            Modeling data and the approaches
            Data denormalization
            Using an array of objects datatype
            Nested object mapping datatypes
            Join datatypes
            Parent ID query
            has_child query
            has_parent query
            Practical considerations

Aggregation Frameworks
            ETF historical data preparation
            Aggregation query syntax
            Matrix aggregations
            Matrix stats
            Metrics aggregations
            avg
            weighted_avg
            cardinality
            value_count
            sum
            min
            max
            stats
            extended_stats
            top_hit
            percentiles
            percentile_ranks
            median_absolute_deviation
            geo_bound
            geo_centroid
            scripted_metric
            Bucket aggregations
            histogram
            date_histogram
            auto_date_histogram
            ranges
            date_range
            ip_range
            filter
            filters
            term
            significant_terms
            significant_text
            sampler
            diversified_sampler
            nested
            reverse_nested
            global
            missing
            composite
            adjacency_matrix
            parent
            children
            geo_distance
            geohash_grid
            geotile_grid
            Pipeline aggregations
            Sibling family
            avg_bucket
            max_bucket
            min_bucket
            sum_bucket
            stats_bucket
            extended_stats_bucket
            percentiles_bucket
            Parent family
            cumulative_sum
            derivative
            bucket_script
            bucket_selector
            bucket_sort
            serial_diff
            Moving average aggregation
            simple
            linear
            ewma
            holt
            holt_winters
            Moving function aggregation
            max
            min
            sum
            stdDev
            unweightedAvg
            linearWeightedAvg
            ewma
            holt
            holtWinters
            Post filter on aggregations

Preprocessing Documents In Ingest Pipelines

            Ingest APIs
            Accessing data in pipelines
            Processors
            Conditional execution in pipelines
            Handling failures in pipelines

Using Elasticsearch For Exploratory Data Analysis
            Business analytics
            Operational data analytics
            Sentiment analysis

Section 3: Programming With The Elasticsearch Client

Elasticsearch From Java Programming

            Overview of Elasticsearch Java REST client
            The Java low-level REST client
            The Java low-level REST client workflow
            REST client initialization
            Performing requests using a REST client
            Handing responses
            Testing with Swagger UI
            New features
            The Java high-level REST client
            The Java high-level REST client workflow
            REST client initialization
            Performing requests using the REST client
            Handling responses
            Testing with Swagger UI
            New features
            Spring Data Elasticsearch

Elasticsearch From Python Programming

            Overview of the Elasticsearch Python client
            The Python low-level Elasticsearch client
            Workflow for the Python low-level Elasticsearch client
            Client initialization
            Performing requests
            Handling responses
            The Python high-level Elasticsearch library
            Illustrating the programming concept
            Initializing a connection
            Performing requests
            Handling responses
            The query class
            The aggregations class

Section 4: Elastic Stack
Using Kibana, Logstash, And Beats

            Overview of the Elastic Stack
            Running the Elastic Stack with Docker
            Running Elasticsearch in a Docker container
            Running Kibana in a Docker container
            Running Logstash in a Docker container
            Running Beats in a Docker container

Working With Elasticsearch SQL

            Overview
            Getting started
            Elasticsearch SQL language
            Reserved keywords
            Data type
            Operators
            Functions
            Aggregate
            Grouping
            Date-time
            Full-text search
            Mathematics
            String
            Type conversion
            Conditional
            System
            Elasticsearch SQL query syntax
            New features
            Elasticsearch SQL REST API
            Elasticsearch SQL JDBC
            Upgrading Elasticsearch from a basic to a trial license
            Workflow of Elasticsearch SQL JDBC
            Testing with Swagger UI

Working With Elasticsearch Analysis Plugins

            What are Elasticsearch plugins?
            Plugin management
            Working with the ICU Analysis plugin
            Examples
            Working with the Smart Chinese Analysis plugin
            Examples
            Working with the IK Analysis plugin
            Examples
            Configuring a custom dictionary in the IK Analysis plugin

Section 5: Advanced Features

Machine Learning With Elasticsearch

            Machine learning with Elastic Stack
            Machine learning APIs
            Machine learning jobs
            Sample data
            Running a single-metric job
            Creating index patterns
            Creating a new machine learning job
            Examining the result
            Machine learning using Elasticsearch and scikit-learn

Spark And Elasticsearch For Real-Time Analytics

            Overview of ES-Hadoop
            Apache Spark support
            Real-time analytics using Elasticsearch and Apache Spark
            Building a virtual environment to run the sample ES-Hadoop project
            Running the sample ES-Hadoop project
            Running the sample ES-Hadoop project using a prepared Docker image

Building Analytics RESTful Services

            Building a RESTful web service with Spring Boot
            Project program structure
            Running the program and examining the APIs
            Main workflow anatomy
            Building the analytic model
            Performing daily update data
            Getting the registered symbols
            Building the scheduler
            Integration with the Bollinger Band
            Building a Java Spark ML module for k-means anomaly detection
            Source code
            Testing Analytics RESTful services
            Testing the build-analytics-model API
            Testing the get-register-symbols API
            Working with Kibana to visualize the analytics results
