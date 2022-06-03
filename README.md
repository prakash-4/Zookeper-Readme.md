# Zookeper Package 

Apache ZooKeeper provides a reliable, centralized register of configuration data and services for distributed applications.

## Configuration Reference

You can configure the following:

### Traffic Exposure parameters

|Parameter|Description|Type|Default|
|---------|-----------|----|-------|			
|service.type|Kubernetes Service type|string|ClusterIP|
|ports.client|ZooKeeper client service port|integer|2181|
|ports.follower|ZooKeeper follower service port|integer|2888|
|ports.election|ZooKeeper election service port|integer|3888|
|networkPolicy.enabled|Specifies whether a NetworkPolicy should be created|string|false|
|publishNotReadyAddresses|If the ZooKeeper headless service should publish DNS records for not ready pods|string|true|

### Metrics parameters

|Parameter|Description|Type|Default|
|---------|-----------|----|-------|
|service.type|ZooKeeper Prometheus Exporter service type|string|ClusterIP|
|service.port|ZooKeeper Prometheus Exporter service port|integer|9141|
|metrics.serviceMonitor.enabled|Create ServiceMonitor Resource for scraping metrics using Prometheus Operator|string|false|
|metrics.prometheusRule.enabled|Create a PrometheusRule for Prometheus Operator|string|false|
			
### ZooKeeper chart parameters 

|Parameter|Description|Type|Default|
|---------|-----------|----|-------|
|auth.enabled|Enable ZooKeeper auth. It uses SASL/Digest-MD5|string|false|
			
### Statefulset parameters

|Parameter|Description|Type|Default|
|---------|-----------|----|-------|
|startupProbe.enabled|Enable startupProbe on ZooKeeper containers|string|false|	
|pdb.maxUnavailable|Maximum unavailable ZooKeeper replicas|integer|1|
|podManagementPolicy|StatefulSet controller supports relax its ordering guarantees while preserving its uniqueness and identity guarantees. There are two valid pod  management policies: OrderedReady and Parallel|string|Parallel|	
|podSecurityContext.fsGroup|Set ZooKeeper pod's Security Context fsGroup|integer|1001|	
|containerSecurityContext.runAsNonRoot|Set ZooKeeper containers' Security Context runAsNonRoot|string|true|	
|containerSecurityContext.runAsUser|Set ZooKeeper containers' Security Context runAsUser|integer|1001|
|livenessProbe.failureThreshold|Failure threshold for livenessProbe|integer|6|	
|livenessProbe.initialDelaySeconds|Initial delay seconds for livenessProbe|integer|30|
|startupProbe.initialDelaySeconds|Initial delay seconds for startupProbe|integer|30|	
|livenessProbe.periodSeconds|Period seconds for livenessProbe|integer|10|	
|readinessProbe.periodSeconds|Period seconds for readinessProbe|integer|10|	
|startupProbe.periodSeconds|Period seconds for startupProbe|integer|10|
|livenessProbe.successThreshold|Success threshold for livenessProbe|integer|1|	
|readinessProbe.successThreshold|Success threshold for readinessProb|integer|1|	
|startupProbe.successThreshold|Success threshold for startupProbe|integer|1|
|livenessProbe.timeoutSeconds|Timeout seconds for livenessProbe|integer|5|
|readinessProbe.timeoutSeconds|Timeout seconds for readinessProbe|integer|5|	

### Volume Permissions parameters

|Parameter|Description|Type|Default|
|---------|-----------|----|-------|
|volumePermissions.enabled|Enable init container that changes the owner and group of the persistent volume|string|false|

### TLS/SSL parameters

|Parameter|Description|Type|Default|
|---------|-----------|----|-------|
|tls.client.enabled|Enable TLS for client connections|string|false|
|tls.quorum.enabled|Enable TLS for quorum protocol|string|false|

### Persistence parameters

|Parameter|Description|Type|Default|
|---------|-----------|----|-------|
|persistence.size|"	PVC Storage Request for ZooKeeper data volume"|string|8Gi|


				
