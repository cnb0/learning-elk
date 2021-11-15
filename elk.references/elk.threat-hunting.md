Section 1: Introduction To Threat Hunting, Analytical Models, And Hunting Methodologies
  
Chapter 1: Introduction To Cyber Threat Intelligence, Analytical Models, And Frameworks
  
            What is cyber threat intelligence?
            The Intelligence Pipeline
            The Lockheed Martin Cyber Kill Chain
            Reconnaissance
            Weaponization
            Delivery
            Exploitation
            Installation
            Command & Control
            Actions on the Objective
            MITRE's ATT&CK Matrices
            The Diamond Model
            Adversary (a)
            Infrastructure (i)
            Victim (v)
            Capabilities (c)
            Motivations
            Directionality
            Strategic, operational, and tactical intelligence
    
      
        
Chapter 2: Hunting Concepts, Methodologies, And Techniques
  
            Introducing threat hunting
            Measuring success
            The Six D's
            The Pyramid of Pain
            Hash values
            IP addresses
            Domain names
            Network/host artifacts
            Tools
            TTPs
            Profiling data
            Expected data
            Detection types
            Machine learning
            Missing data
            Data pattern of life
            Indicators
            The depreciation life cycle
            Indicator decay
            Shunning
            The deprecation pipeline
            The HIPESR model
    
      
        
Section 2: Leveraging The Elastic Stack For Collection And Analysis
  
Chapter 3: Introduction To The Elastic Stack
              
            Introducing Logstash
            Input plugins
            Filter plugins
            Output plugins
            Elasticsearch, the heart of the stack
            Bringing data into Elasticsearch
            Beats and Agents
            Filebeat
            Packetbeat
            Winlogbeat
            Elastic Agent
            Viewing Elasticsearch data with Kibana
            Using Kibana to view Elasticsearch data
            Elastic solutions
            Enterprise Search
            Observability
            Security
    
      

Chapter 4: Building Your Hunting Lab – Part 1
  
            Your lab architecture
            Hypervisor
            Building an Elastic machine
            Creating the Elastic VM
            Installing CentOS
            Enabling the internal network interface
            Installing VirtualBox Guest Additions
    
      
Chapter 5: Building Your Hunting Lab – Part 2
  
            Installing and configuring Elasticsearch
            Adding the Elastic repository
            Installing Elasticsearch
            Securing Elasticsearch
            Installing Elastic Agent
            Installing and configuring Kibana
            Installing Kibana
            Connecting Kibana to Elasticsearch
            Connecting to Kibana from a browser
            Enabling the detection engine and Fleet
            Detection engine
            Fleet
            Enrolling Fleet Server
            Building a victim machine
            Collecting the operating systems
            Creating the virtual machine
            Installing Windows
            Filebeat Threat Intel module
    
      
        
Chapter 6: Data Collection With Beats And Elastic Agent
  
            Data flow
            Configuring Winlogbeat and Packetbeat
            Installing Beats
            Configuring Sysmon for endpoint collection
            Configuring Elastic Agent
            Deploying Elastic Agent
    
      
        
Chapter 7: Using Kibana To Explore And Visualize Data
  
            The Discover app
            The spaces selector
            The search bar
            The filter controller
            The Index Pattern selector
            The field name search bar
            The field type search
            Available fields
            The Kibana search bar
            The query language selector
            The date picker
            The Action menu
            Support information
            The search/refresh button
            The timebox
            The Event view
            Exercise
            Query languages
            Lucene
            KQL
            EQL
            The Visualize app
            Considerations
            The data table
            Bar charts
            Pie charts
            Line charts
            Others
            Lens
            Exercise
            The Dashboard app
    
      
        
Chapter 8: The Elastic Security App

            The Elastic Security app overview
            The detection engine
            Managing detection rules
            Creating a detection rule
            Trend timeline
            Hosts
            Network
            Timelines
            Cases
            Administration
    
      
        
Section 3: Operationalizing Threat Hunting
  
Chapter 9: Using Kibana To Pivot Through Data To Find Adversaries
              
            Connecting events with a timeline
            Using observations to perform targeted hunts
            Pivoting to find more infections
            Generating tailored detection logic
    
      
        
Chapter 10: Leveraging Hunting To Inform Operations
              
            An overview of incident response
            Preparation
            Detection and analysis
            Containment
            Eviction
            Recovery
            Lessons learned
            Using threat hunting information to assist IR
            Prioritizing improvements to the security posture
            Lockheed Martin Cyber Kill Chain
            Using external information to drive hunting techniques
    
      
        
Chapter 11: Enriching Data To Make Intelligence
  
            Enhancing analysis with open source tools
            MITRE ATT&CK Navigator
            Enriching events with third-party tools
            IPinfo
            Abuse.ch's ThreatFox
            VirusTotal
            Enrichments within Elastic
    
      
        
Chapter 12: Sharing Information And Analysis
  
            The Elastic Common Schema
            Describing data uniformly
            Collecting non-ECS data
            Importing and exporting Kibana saved objects
            Type
            Tags
            Export
            Import
            Developing and contributing detection logic