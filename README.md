:linkattrs:
:project-owner:      redis-field-engineering
:project-name:       redis-cloud-datadog-prometheus-collector
:name:               Redis Cloud DataDog Prometheus Collector

The {name} collects metrics from a Redis Cloud subscription using Prometheus and then exports those metrics to DataDog. This project is provided as a Docker image for ease of use.

== Table of Contents

* link:#Requirements[Requirements]
* link:#Usage[Usage]
* link:#Support[Support]

== Requirements

To use the {name}, you will need:

* A Redis Cloud account with a https://docs.redis.com/latest/rc/subscriptions/create-flexible-subscription/[Flexible or Annual subscription]
* A https://www.datadoghq.com/[DataDog account]
* A container runtime that is https://docs.redis.com/latest/rc/security/vpc-peering/[VPC-peered with your Redis Cloud subscription]

Additionally, you will need the following information:

* A https://docs.datadoghq.com/account_management/api-app-keys/[DataDog API key]
* The https://docs.redis.com/latest/rc/databases/view-edit-database/[private endpoint] for one of the databases associated with your Redis Cloud subscription
* The https://docs.redis.com/latest/rc/api/get-started/manage-api-keys/[API account] key for your Redis Cloud account
* An https://docs.redis.com/latest/rc/api/get-started/manage-api-keys/[API user key] for your Redis Cloud account

== Usage

You can run the container as follows. Note that all of the specified environment variables are required:

```
docker run -e DATADOG_API_KEY=<API_KEY> \
           -e DATADOG_SITE=datadoghq.com \
		   -e REDIS_CLOUD_ENDPOINT_URL=<REDIS_CLOUD_ENDPOINT> \
		   -e REDIS_CLOUD_API_ACCOUNT_KEY=<SECRET_ACCOUNT_KEY> \
		   -e REDIS_CLOUD_API_SECRET=<SECRET_USER_KEY> \
		   kbredis/ddtest
```

== Support

{name} is supported by Redis, Inc. on a good faith effort basis. To report bugs, request features, or receive assistance, please https://github.com/{project-owner}/{project-name}/issues[file an issue].
