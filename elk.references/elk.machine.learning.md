
Machine Learning For IT

            Overcoming the historical challenges
            The plethora of data
            The advent of automated anomaly detection
            Theory of operation
            Defining unusual
            Learning normal, unsupervised
            Probability models
            Learning the models
            De-trending
            Scoring of unusualness
            Operationalization
            Jobs
            ML nodes
            Bucketization
            The datafeed
            Supporting indices
            .ml-state
            .ml-notifications
            .ml-anomalies-*
            The orchestration

Installing The Elastic Stack With Machine Learning
            
            Installing the Elastic Stack
            Installing Elasticsearch
            Installing Kibana
            Enabling Platinum features
            A guided tour of Elastic ML features
            Getting data for analysis
            ML job types in Kibana
            Data Visualizer
            The Single metric job
            Multi-metric job
            Population job
            Advanced job
            Controlling ML via the API

Event Change Detection
            
            How to understand the normal rate of occurrence
            Exploring count functions
            Summarized counts
            Splitting the counts
            Other counting functions
            Non-zero count
            Distinct count
            Counting in population analysis
            Detecting things that rarely occur
            Counting message-based logs via categorization
            Types of messages that can be categorized by ML
            The categorization process
            Counting the categories
            Putting it all together
            When not to use categorization

IT Operational Analytics And Root Cause Analysis
            
            Holistic application visibility
            The importance and limitations of KPIs
            Beyond the KPIs
            Data organization
            Effective data segmentation
            Custom queries for ML jobs
            Data enrichment on ingest
            Leveraging the contextual information
            Analysis splits
            Statistical influencers
            Bringing it all together for root cause analysis
            Outage background
            Visual correlation and shared influencers

Security Analytics With Elastic Machine Learning

            Security in the field
            The volume and variety of data
            The geometry of an attack
            Threat hunting architecture
            Layer-based ingestion
            Threat intelligence
            Investigation analytics
            Assessment of compromise

Alerting On ML Analysis

            Results presentation
            The results index
            Bucket results
            Record results
            Influencer results
            Alerts from the Machine Learning UI in Kibana
            Anatomy of the default watch from the ML UI in Kibana
            Creating ML alerts manually

Using Elastic ML Data In Kibana Dashboards

            Visualization options in Kibana
            Visualization examples
            Timelion
            Time series visual builder
            Preparing data for anomaly detection analysis
            The dataset
            Ingesting the data
            Creating anomaly detection jobs
            Global traffic analysis job
            A HTTP response code profiling of the host making requests
            Traffic per host analysis
            Building the visualizations
            Configuring the index pattern
            Using ML data in TSVB
            Creating a correlation Heat Map
            Using ML data in Timelion
            Building the dashboard

Using Elastic ML With Kibana Canvas

            Introduction to Canvas
            What is Canvas?
            The Canvas expression
            Building Elastic ML Canvas slides
            Preparing your data
            Anomalies in a Canvas data table
            Using the new SQL integration

Forecasting

            Forecasting versus prophesying
            Forecasting use cases
            Forecasting – theory of operation
            Single time series forecasting
            Dataset preparation
            Creating the ML job for forecasting
            Forecast results
            Multiple time series forecasting

ML Tips And Tricks

            Job groups
            Influencers in split versus non-split jobs
            Using ML on scripted fields
            Using one-sided ML functions to your advantage
            Ignoring time periods
            Ignoring an upcoming (known) window of time
            Creating a calendar event
            Stopping and starting a datafeed to ignore the desired timeframe
            Ignoring an unexpected window of time, after the fact
            Clone the job and re-run historical data
            Revert the model snapshot
            Don't over-engineer the use case
            ML job throughput considerations
            Top-down alerting by leveraging custom rules
            Sizing ML deployments
