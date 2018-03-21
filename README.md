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
The Splunk Add-on for Instana contains a global configuration for your Instana account URL and API authorization token.  Enter those values on the **Configuration** tab in the Add-on.

From the Inputs menu, create new Input for the data you wish to collect.  Each Input requires 4 parameters:
  - Input Name 
  - Pollling interval
  - Splunk Index to use
  - Instana search filter that you would like to run
  
  To retrieve metrics for all web applications and websites use: 
  ```
  entity.pluginId:logicalwebapp OR entity.pluginId:browserLogicalService
  ```
  To retrieve metrics for all databases: 
  ```
  entity.selfType:database 
  ```
**Note:** This Add-on can be used for entities (Instana Snapshots) that contains the following 4 metrics:  
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
