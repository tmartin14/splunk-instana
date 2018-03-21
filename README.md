# splunk-instana
Splunk Integration Add-On for Instana data

## What's Needed?
- Downloads
    - Splunk Add-on for Instana
    - Splunk App for Instana


- Instana Information Required
    - Instana API base URL   (https://<your account>.instana.io)
    - Instana API Authorization Token
    
## Installation
The installation consists of installing both the *Splunk Add-on for Instana* and the *Splunk App for Instana*.   
  - The Add-on is responsible for executing the rest API calls and collecting the data from Instana.  
  - The App provides a collection of dashboards and saved searches.  
  
To install, navigate to Apps --> Manage Apps and select the “Install app from File” button.  Specify the location of the file you downloaded and install it.   

## Configuration
The Splunk Add-on for Instana contains a global configuration for your Instana account URL and API authorization token.  In the Add-on, navigate to the Configuration tab and enter these values.  
This Add-on also contains single input type, *Instana Metrics*. From the Inputs menu, enter the parameters for your input:
  - Name your input
  - Set the pollling interval
  - Select the appropriate index
  - Copy your Instana search query that you would like to run. 
To retrieve metrics for all web applications and websites use: 
  ```
  entity.pluginId:logicalwebapp OR entity.pluginId:browserLogicalService
  ```
**Note:** This Add-on can be used for any entity (Instana Snapshot) that contains any of the following 4 metrics:  
  - latency     ==> Average Response Time
  - count       ==> Calls per second
  - error_rate  ==> Error Rate
  - instances   ==> number of instances running this entity


## Start Searching
Once the Splunk Add-on for Instana is installed and configured you can execute searches using: 
```
sourcetype="instana:metrics"
```

----  
