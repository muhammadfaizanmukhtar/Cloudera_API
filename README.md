# Cloudera_API
Basic API't to access the cluster via API's

Cluster details:

curl -u username:password -X GET "http://{CMIPADDRESS}:7180/api/v54/clusters?clusterType=ANY&view=SUMMARY" -H "accept: application/json"

All Hosts details:

curl -u username:password -X GET "http://{CMIPADDRESS}:7180/api/v54/clusters/{ClusterName}/hosts?view=SUMMARY" -H "accept: application/json"

All services details:

curl -u username:password -X GET "http://{CMIPADDRESS}:7180/api/v54/clusters/{ClusterName}/services" -H "accept: application/json"

Stopping oozie service:

curl -u username:password -X POST "http://{CMIPADDRESS}:7180/api/v54/clusters/{ClusterName}/services/oozie/commands/stop" -H "accept: application/json"

Starting oozie service:

curl -u username:password -X POST "http://{CMIPADDRESS}:7180/api/v54/clusters/{ClusterName}/services/oozie/commands/start" -H "accept: application/json"


Collect Host Statistics Globally Command:

curl -u username:password -X POST "http://{CMIPADDRESS}:7180/api/v54/cm/commands/collectDiagnosticData" -H "accept: application/json" -H "Content-Type: application/json" -d "{ \"collectCMDBDump\": true, \"bundleSizeBytes\": 10240, \"startTime\": \"2025-03-10T12:00:00Z\", \"endTime\": \"2025-03-11T12:00:00Z\", \"clusterName\": \"{ClusterName}\", \"enableMonitorMetricsCollection\": true, \"phoneHome\": true}"
