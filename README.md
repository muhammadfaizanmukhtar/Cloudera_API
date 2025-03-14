**Cloudera_API's:**

Cloudera provides a comprehensive suite of APIs that enable users to interact programmatically with its data management platform. These APIs allow for automation, integration, and customization of various operations within the Cloudera ecosystem, which is used for big data management, analytics, and machine learning. Below is a summary of the key Cloudera APIs:

The username and password in all API's will be cloudera manager username and password.

**Cluster details:**

curl -u username:password -X GET "http://{CMIPADDRESS}:7180/api/v54/clusters?clusterType=ANY&view=SUMMARY" -H "accept: application/json"

**All Hosts details:**

curl -u username:password -X GET "http://{CMIPADDRESS}:7180/api/v54/clusters/{ClusterName}/hosts?view=SUMMARY" -H "accept: application/json"

**All services details:**

curl -u username:password -X GET "http://{CMIPADDRESS}:7180/api/v54/clusters/{ClusterName}/services" -H "accept: application/json"

**Stopping oozie service:**

curl -u username:password -X POST "http://{CMIPADDRESS}:7180/api/v54/clusters/{ClusterName}/services/oozie/commands/stop" -H "accept: application/json"

**Starting oozie service:**

curl -u username:password -X POST "http://{CMIPADDRESS}:7180/api/v54/clusters/{ClusterName}/services/oozie/commands/start" -H "accept: application/json"

**Collect Host Statistics Globally Command:**

curl -u username:password -X POST "http://{CMIPADDRESS}:7180/api/v54/cm/commands/collectDiagnosticData" -H "accept: application/json" -H "Content-Type: application/json" -d "{ \"collectCMDBDump\": true, \"bundleSizeBytes\": 10240, \"startTime\": \"2025-03-10T12:00:00Z\", \"endTime\": \"2025-03-11T12:00:00Z\", \"clusterName\": \"{ClusterName}\", \"enableMonitorMetricsCollection\": true, \"phoneHome\": true}"

**Official documentation:**
https://archive.cloudera.com/cm7/7.11.3.0/generic/jar/cm_api/apidocs/resource_ClustersResource.html
