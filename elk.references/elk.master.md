
1. Elastic Stack Overview
  
            Introduction to ELK Stack
            Logstash
            Elasticsearch
            Kibana
            The birth of Elastic Stack
            Beat
            Who uses Elastic Stack?
            Salesforce
            CERN
            Green Man Gaming
            Stack competitors
            Setting up Elastic Stack
            Installation of Java
            Installation of Java on Ubuntu 14.04
            Installation of Java on Windows
            Installation of Elasticsearch
            Installation of Elasticsearch on Ubuntu 14.04
            Installation of Elasticsearch on Windows
            Installation of Elasticsearch as a service
            Installation of Kibana
            Installation of Kibana on Ubuntu 14.04
            Installation of Kibana on Windows
            Installation of Logstash
            Installation of Logstash on Ubuntu 14.04
            Installation of Logstash on Windows
            Installation of Filebeat
            Installation of Filebeat on Ubuntu 14.04
            Installation of Filebeat on Windows
            X-Pack
  
  
2. Stepping into Elasticsearch
  
            The beginning of Elasticsearch
            Key features
            Understanding the architecture
            Recommended cluster configurations
            Minimum master nodes
            Local cluster settings
            Understanding document processing
            Elasticsearch APIs
            Document APIs
            Single document APIs
            Index API
            Get API
            Delete API
            Update API
            Multi-document APIs
            Multi-get API
            Bulk API
            Search APIs
            Search API
            Query parameters
            Search shard API
            Multi-search APIs
            Count API
            Validate API
            Explain API
            Profile API
            Field stat API
            Indices APIs
            Managing indices
            Creating an index
            Checking if an index exists
            Getting index information
            Managing index settings
            Getting index stats
            Getting index segments
            Getting index recovery information
            Getting shard stores information
            Index aliases
            Mappings
            Closing, opening, and deleting an index
            Other operations
            Cat APIs
            Cluster APIs
            Query DSL
            Aggregations
            Bucket
            Metrics aggregations
            Avg aggregation
            Min aggregation
            Max aggregation
            Percentiles Aggregation
            Sum aggregation
            Value count aggregation
            Cardinality aggregation
            Stats aggregation
            Extended stats aggregation
            A note for painless scripting
 
3. Exploring Logstash and Its Plugins
  
            Introduction to Logstash
            Why do we need Logstash?
            Features of Logstash
            Logstash Plugin Architecture
            Logstash Configuration File Structure
            Value types
            Array
            Boolean
            Bytes
            Codec
            Comments
            Hash
            Number
            String
            Use of Conditionals
            Types of Plugins
            Input plugins
            Filter plugins
            Output plugins
            Codec plugins
            Exploring Input Plugins
            stdin
            file
            path
            udp
            Exploring Filter Plugins
            grok
            mutate
            csv
            Exploring Output Plugins
            stdout
            file
            elasticsearch
            Exploring Codec Plugins
            rubydebug
            json
            avro
            multiline
            Plugins Command-Line Options
            Listing of Plugins
            Installing a plugin
            Removing a plugin
            Updating a plugin
            Packing a plugin
            Unpacking a plugin
            Logstash command-line options
            Logstash Tips and Tricks
            Referencing fields and Its values
            Adding custom-created grok patterns
            Logstash does not show any output
            When an input file has already been completely read
            When an input file is not modified since 1 day
            Logstash Configuration for Parsing Logs
            Sample Catalina logs
            Sample Tomcat logs
            Grok pattern for Catalina logs
            Grok pattern for Tomcat logs
            Logstash configuration file
            Monitoring APIs
            Node info API
            OS Info
            JVM info
            Pipleine Info
            Plugins Info API
            Node stats API
            JVM stats
            Process stats
            Pipeline stats
            Hot threads API
            Threads
            Human
            Ignore idle threads
    
  
4. Kibana Interface
  
            Kibana and its offerings
            Kibana interface
            Exploring the discover interface
            Time Filter
            Quick time filter
            Relative time filter
            Absolute time filter
            Auto-refresh
            Querying and Searching data
            Full-text searches
            Range searches
            Boolean searches
            Proximity search
            Wildcard searches
            Regular expressions search
            Grouping
            Fields and filters
            Filtering the field
            Functionalities of filters
            Discovery page options
            Exploring the visualize interface
            Understanding aggregations
            Bucket aggregations
            Metric aggregations
            Visualization Canvas
            Area chart
            Data table
            Line chart
            Bubble chart
            Markdown widget
            Metric
            Pie chart
            Tag clouds
            Tile map
            Time series
            Vertical bar chart
            Exploring the Dashboard interface
            Understanding Timelion
            Exploring Dev Tools
            Exploring the Management interface
            Index patterns
            Saved objects
            Advanced Settings
            Status
            Putting it all together
            Input data
            Creating a Logstash configuration file
            Using Kibana
            Top states based on 2003 RUCC
            Top states based on 2003 UIC
            Top five area names with less than high school diploma 1970
            Top five area names with high school diploma 1970
            Percentage of adults having less than high school diploma in 1970 by area and state
            Top states  as per their count and their top 2013 RUCC
            Insights
            Creating a dashboard in Kibana
    
  
5. Using Beats
  
            Introduction to Beats
            How Beats differ from Logstash
            How Beats fits into Elastic Stack
            An overview of the different types of Beats
            Beats by Elastic Team
            Packetbeat
            Metricbeat
            Filebeat
            Winlogbeat
            Libbeat
            Beats by community
            Dockbeat
            Lmsensorbeat
            Exploring Elastic Team Beats
            Understanding Filebeat
            Filebeat Prospectors Configuration
            Processors configuration
            Defining a processor
            Output Configuration
            Elasticsearch Output Configuration
            Logstash Output Configuration
            Logging Configuration
            Understanding Metricbeat
            System Module
            CPU metricset
            Disk I/O metricset
            Filesystem metricset
            FsStat metricset
            Load metricset
            Memory metricset
            Network metricset
            Process Metricset
            Installation of Metricbeat
            Installation of Metricbeat on Ubuntu 14.04
            Understanding Packetbeat
            Installation of Packetbeat
            Installation of Packetbeat on Ubuntu 14.04
            Exploring Community Beats
            Understanding Elasticbeat
            Installation of Elasticbeat
            Installation of Elasticbeat on Ubuntu 14.04
            Elasticbeat configuration
            Beats in action with Elastic Stack
            Exploring Metricbeat with Logstash and Kibana
            Step 1-Configuring Metricbeat to send data to Logstash
            Step 2-Creating a Logstash configuration file
            Step 3-Downloading and loading the sample Beats dashboard
            Step 4-Viewing the sample Beats dashboard
            Exploring Elasticbeat with Elasticsearch and Kibana
            Step 1-Configuring Elasticbeat to send data to Elasticsearch
            Step 2-Downloading and loading the Elasticbeat dashboard
            Step 3-Viewing the sample Beats dashboard
    
  
6. Elastic Stack in Action
  
            Understanding problem scenario
            Understanding the architecture
            Preparing Elastic Stack pipeline
            What to capture?
            Updated architecture
            Configuring Elastic Stack components
            Setting up Elasticsearch
            Setting up agents/Beats
            Packetbeat
            Metricbeat
            Filebeat
            Setting up Logstash
            grok for nginxlogs
            grok for liferaylogs
            grok for openDJ logs.
            Config File
            Setting up Kibana
            Setting up Kibana Dashboards
            PacketBeat
            MetricBeat
            Checking DB (MySQL) Performance
            Analyzing CPU usage
            Keeping an eye on memory
            Checking logs
            Finding most visited pages
            Visitors' map
            Number of visitors in a time frame
            Request Types
            Error type-log levels
            Top referrers
            Top agents
            Alerting using Logstash e-mail capability
            Using a message broker
  
    
  
7. Customizing Elastic Stack
  
            Extending Elasticsearch
            Elasticsearch development environment
            Anatomy of an Elasticsearch Java plugin
            Building the plugin
            Extending Logstash
            Generating a plugin
            Anatomy of the plugin
            weather.rb file
            Plugin logic implementation
            Reading data from API end point
            Preparing an event
            Publish the event
            Building and installing a plugin
            Testing our plugin
            Extending Beats
            libbeat framework
            Creating a beat
            Anatomy of a Beat
            Beat configuration
            weatherbeat.go file
            Implementing beat logic
            Adding the Configuration
            Reading data from API
            Parsing the data
            Preparing an event
            Publishing the event
            Running the beat
            Extending Kibana
            Setting up Kibana development environment
            Generating the plugin
            Anatomy of a plugin
    
  
8. Elasticsearch APIs
  
            The cluster APIs
            Cluster health
            Cluster State
            Cluster stats
            Pending tasks
            Cluster reroute
            Cluster update settings
            Node stats
            Nodes info API
            Task Management API
            The cat APIs
            Elasticsearch modules
            Cluster module
            Discovery module
            Gateway module
            HTTP module
            Indices module
            Network module
            Node client
            Plugins module
            Scripting
            Snapshot/restore module
            Thread pools
            Transport module
            Tribe nodes module
            Ingest nodes
            Elasticsearch clients
            Supported clients
            Community contributed clients
            Java API
            Connecting to a Cluster
            Admin tasks
            Managing indices
            Creating an index
            Getting index settings
            Updating index settings
            Refreshing an index
            Managing clusters
            Getting cluster tasks
            Getting cluster health
            Index-level tasks
            Managing documents
            Indexing a document
            Getting a document
            Deleting a document
            Updating a document
            Query DSL and search API
            Aggregations
            Elasticsearch plugins
            Discovery plugins
            Ingest plugins
            Elasticsearch SQL
    
  
9. X-Pack: Security and Monitoring
  
            Introduction to X-Pack
            Installation of X-Pack
            Installing X-Pack in Elasticsearch
            Installing X-Pack in Kibana
            Installing X-Pack on offline systems
            Uninstalling X-Pack
            Security
            Listing of all users in security
            Listing of roles in security
            Understanding roles in security
            Understanding Cluster Privileges
            Understanding Run As privileges
            Understanding Indices privileges
            Decoding default user roles
            kibana_user
            superuser
            transport_client
            Adding a role in security
            Updating a role in security
            Understanding Field Level Security
            Adding a user in security
            Updating user details in security
            Changing the password of a user in security
            Deleting a role in security
            Deleting a user in security
            Viewing X-Pack information
            Enabling and disabling of X-Pack features
            Monitoring
            Exploring monitoring statistics for Elasticsearch
            Discovering the Overview tab
            Discovering the Indices tab
            Discovering the Nodes tab
            Exploring monitoring statistics for Kibana
            Understanding Profiler
  
    
  
10. X-Pack: Alerting, Graph, and Reporting
  
            Alerting and notification
            Working of watcher
            Trigger
            Schedule trigger
            Input
            Simple input
            Search input
            HTTP input
            Chain input
            Conditions
            Always condition
            Never condition
            Compare condition
            Array compare condition
            Script condition
            Transforms
            Search transform
            Script transform
            Chain transform
            Actions
            Throttling
            Graph
            Working of Graph
            Graph UI
            Reporting
  
11. Best Practices
  
            Why do we require best practices?
            Understanding your use case
            Managing configuration files
            Elasticsearch - elasticsearch.yml
            Kibana - kibana.yml
            Choosing the right set of hardware
            Memory
            Java heap size
            Swapping memory
            Disks
            Sizing disk space
            I/O
            CPU
            Network
            Searching and indexing performance
            Filter cache
            Fielddata size
            Indexing buffer
            Sizing the Elasticsearch cluster
            Choosing the right kind of node
            Master and data node
            Master node
            Data node
            Ingest node
            No master, no data, and no ingest node
            Determining the number of nodes
            Determining the number of shards
            Reducing disk space
            Logstash configuration file
            Categorizing multiple sources of data
            Using conditionals
            Using custom grok patterns
            Simplifying _grokparsefailure
            Mapping of fields
            Dynamic templating
            Testing configuration
            Re-indexing data
            Using aliases
    
  
12. Case Study-Meetup
  
            Understanding meetup scenario
            Setting things up
            A bit of Meetup API understanding
            Setting up Elasticsearch
            Preparing Logstash
            Setting up Kibana
            Analyzing data using Kibana
            Filtering Content
            Number of Meetups by Country
            Top 10 meetup cities in world
            Meetups trends by duration
            Meetups by RSVP Counts
            Number of Groups by country
            Number of Groups by join mode
            Popular Categories
            Popular Topics
            Meetup Venue Map
            Meetups on Map
            Just the number of things