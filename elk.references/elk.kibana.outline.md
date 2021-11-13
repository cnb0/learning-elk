- Intro to Kibana

        What is Kibana? What is it used for, and what can we do with it?

        Overview of installation options
            When it comes to installing Kibana (and Elasticsearch), we have a couple of options 

        Running Elasticsearch & Kibana in Elastic Cloud
            how to create an Elasticsearch and Kibana deployment on Elastic Cloud, 
            which is usually the easiest and fastest way to get started learning Kibana.

        Installing Elasticsearch
             Kibana requires an Elasticsearch cluster
             to get the most out of Kibana, we need to activate a trial license. 
             This way, we can access and use all Kibana features. 
             This is only required for local Kibana deployments/installations.
        
        Dev Console 
            Console tool, which is used to send queries to Elasticsearch.

        Adding index templates
            Before importing the test data  add two so-called index templates. 

        Importing test data
            Kibana is not much fun without any data, so let's import some test data. 
            We will be working with two datasets ; one for HTTP access logs, and one for orders.

        Introduction to the test data
             test data and which fields it contains.

        Creating index patterns
            create two index patterns. 


- Introduction to interface 

        Setting the time filter
            When working with data within Kibana, we need to define which time period we would like to see data for. 
            This is especially the case since our test data is dated back to the beginning of 2020. 
            learn various ways of using Kibana's time filter.

        Kibana Query Language (KQL)
             what the Kibana Query Language — or KQL — is. 
             
        Discover app
            Discover app, being where we can filter and search for documents.

        Saving queries
            Unlike saving searches, save queries Learn the difference between the two.

        Inspecting requests
            Sometimes it might be useful to see which requests Kibana sends to Elasticsearch on our behalf 
            how to inspect the requests in this lecture.

        How Kibana handles time zones
            Kibana does a bit of time zone conversion when working with timestamps, both 
            in regards to the time filter and document fields.
            how this time zone conversion works.

        Changing Kibana’s time zone
            Sometimes we might not want Kibana to convert timestamps to our local time zone. Learn 
            how to change Kibana's time zone to avoid this.


- Intro to Visualization
        
        Introduction to aggregations
            Before getting started with visualizations, you need to understand the basics of 
            Elasticsearch aggregations. 

        Metric visualization
             As the first visualization type, let's look at the Metric visualization, 
             which simply presents a numeric value.

        Formatting numbers
            Sometimes we might want to change how numbers are formatted. Learn how to change 
            how a field's value is displayed — not just numeric fields.

        Vertical Bar
            Let's look at a slightly more interesting visualization type, namely the Vertical Bar visualization. 
            Learn how this visualization type can be used to display values over time 

        Area chart
            Although conceptually similar to the Vertical Bar visualization, let's look at how to create an Area chart. 
            While doing so,  show multiple values within the visualization.

        Line chart
            Similar to both the Vertical Bar and Area visualizations, let's look at the Line visualization. 
            Since this visualization type is not much different,being to automatically render multiple line charts.

        Changing the chart type
            Since the Vertical Bar, Area, and Line visualizations are so similar, 
            we can actually switch between them with a visualization option.

        Pie chart
            Let's now take a look at a significantly different visualization type, being pie charts. 
            While doing so, you will see a number of different examples, such as showing the sales channels.
        
        Splitting with KQL filters
            how KQL can be used to split data into multiple series. In particular, an Area visualization 
            with multiple series, where each matches a KQL query.

        Working with numeric ranges
            how to work with numeric ranges. As it turns out, Kibana has a convenient interface for doing so.

        Working with dynamic ranges (histograms)
            Sometimes we might not be able to define ranges ahead of time. By using histograms, we can have 
            Elasticsearch automatically generate ranges for us based on how we configure things within Kibana. 

        Customizing visualizations
            The appearance of visualizations can be customized in many ways. 

        Data tables
            Another way of presenting data within Kibana is within data tables. 
            Data tables themselves are quite simple, a metric named "Top hit."

        Heat maps
            Time for a super cool and useful visualization; heat maps. With heat maps,
            we can visualize magnitude between two values. visualize the number of HTTP requests for the 
            most popular pages during the day.

        Tag clouds
            Time to look at tag clouds, which you might have seen before. A tag cloud is essentially a number of 
            terms with their sizes representing their significance. 
            In our case, we will show the most popular cities from which our HTTP requests come from.

        Goals & Gauges
            The Goal and Gauge visualizations are very similar. For instance, the former can be used to visualize 
            how close we are to reaching a given sales goal, while the latter can show the CPU usage of a server. 

        Linking visualizations to saved searches
             Visualizations can actually be linked to saved searches, which is a great way of reusing searches. 

        Applying saved queries to visualizations
             Instead of linking visualizations to saved searches, we can also apply saved queries to them. 


- Dashboards

        Creating a dashboard
            Time to create our first dashboard. Specifically, one for the orders dataset. 
            Along the way, you will learn the basics of dashboards and how to place visualizations on them.

        Editing visualizations
            Now that our dashboards contains a couple of visualizations, let's look at how we can edit them. 

        Filtering documents
            As with the Discover app, we can also filter documents on dashboards

        Inspecting panels
            Earlier in the course you saw how to inspect which requests Kibana sends to Elasticsearch. 
                    
        Creating the access logs dashboard
            HTTP access logs dataset

        Interactivity
            Within dashboards, we can actually interact with our data in a number of ways — 
            besides just filtering the data. 

        Drilldowns
            how to use drilldowns to navigate between dashboards while retaining context.


- User,Role,Spaces

        Enabling security features
        
        Introduction to spaces
             what spaces are and how they can be used to configure Kibana feature visibility.

        Copying objects between spaces
            Kibana objects are stored within spaces, so let's see how we can copy objects between spaces.

        Creating and managing users
            Using Kibana with just a single user is not recommended, so let's see how to create and manage users.

        Introduction to roles
             roles and what we can do with them. We will start out simple and use preconfigured 
             roles before creating our own ones  

        Configuring privileges with custom roles
             Now that we have made use of preconfigured roles, let's see how we can create our own ones.

        Combining space and role privileges
            Spaces configure feature visibility. Roles configure feature privileges from a security perspective. 
            But what happens if we combine the two? Which features will then be available to users?  

        How role privileges are merged
            What happens if a user contains multiple roles and the roles define privileges to the 
            same Kibana features? Which role takes precedence? 
            how role privileges are merged together.