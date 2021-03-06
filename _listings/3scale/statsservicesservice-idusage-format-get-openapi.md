---
swagger: "2.0"
x-collection-name: 3scale
x-complete: 0
info:
  title: 3Scale Analytics API Service Usage by Metric
  description: Service usage by metric.
  termsOfService: http://www.3scale.net/terms-and-conditions/
  contact:
    name: 3Scale
    url: https://support.3scale.net/
  version: "1"
host: su1.3scale.net
basePath: /
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /admin/api/application_plans/{application_plan_id}/metrics/{metric_id}/limits.xml:
    get:
      summary: Limit List per Metric
      description: Limit list per metric.
      operationId: application_plan_limit
      x-api-path-slug: adminapiapplication-plansapplication-plan-idmetricsmetric-idlimits-xml-get
      parameters:
      - in: path
        name: application_plan_id
        description: id of the application plan
      - in: path
        name: metric_id
        description: id of the metric
      - in: query
        name: provider_key
        description: Your api key with 3scale (also known as provider key)
      responses:
        200:
          description: OK
      tags:
      - Limit
      - List
      - Per
      - Metric
  /admin/api/application_plans/{application_plan_id}/metrics/{metric_id}/pricing_rules.xml:
    get:
      summary: Pricing Rules List per Metric
      description: Pricing rules list per metric.
      operationId: application_plan_pricing_rules
      x-api-path-slug: adminapiapplication-plansapplication-plan-idmetricsmetric-idpricing-rules-xml-get
      parameters:
      - in: path
        name: application_plan_id
        description: id of the application plan
      - in: path
        name: metric_id
        description: id of the metric
      - in: query
        name: provider_key
        description: Your api key with 3scale (also known as provider key)
      responses:
        200:
          description: OK
      tags:
      - Pricing
      - Rules
      - List
      - Per
      - Metric
  /admin/api/services/{service_id}/metrics.xml:
    get:
      summary: Metric List
      description: Metric list.
      operationId: metric
      x-api-path-slug: adminapiservicesservice-idmetrics-xml-get
      parameters:
      - in: query
        name: provider_key
        description: Your api key with 3scale (also known as provider key)
      - in: path
        name: service_id
        description: id of the service
      responses:
        200:
          description: OK
      tags:
      - Metric
      - List
    post:
      summary: Metric Create
      description: Metric create.
      operationId: metric
      x-api-path-slug: adminapiservicesservice-idmetrics-xml-post
      parameters:
      - in: query
        name: friendly_name
        description: Descriptive Name of the metric
      - in: query
        name: name
        description: 'DEPRECATED: Please use system_name parameter'
      - in: query
        name: provider_key
        description: Your api key with 3scale (also known as provider key)
      - in: path
        name: service_id
        description: id of the service
      - in: query
        name: system_name
        description: System Name of the metric
      - in: query
        name: unit
        description: Measure unit of the metric
      responses:
        200:
          description: OK
      tags:
      - Metric
      - Create
  /admin/api/services/{service_id}/metrics/{id}.xml:
    delete:
      summary: Metric Delete
      description: Metric delete.
      operationId: metric
      x-api-path-slug: adminapiservicesservice-idmetricsid-xml-delete
      parameters:
      - in: path
        name: id
        description: id of the metric
      - in: query
        name: provider_key
        description: Your api key with 3scale (also known as provider key)
      - in: path
        name: service_id
        description: id of the service
      responses:
        200:
          description: OK
      tags:
      - Metric
    get:
      summary: Metric Read
      description: Metric read.
      operationId: metric
      x-api-path-slug: adminapiservicesservice-idmetricsid-xml-get
      parameters:
      - in: path
        name: id
        description: id of the metric
      - in: query
        name: provider_key
        description: Your api key with 3scale (also known as provider key)
      - in: path
        name: service_id
        description: id of the service
      responses:
        200:
          description: OK
      tags:
      - Metric
      - Read
    put:
      summary: Metric Update
      description: Metric update.
      operationId: metric
      x-api-path-slug: adminapiservicesservice-idmetricsid-xml-put
      parameters:
      - in: query
        name: friendly_name
        description: Name of the metric
      - in: path
        name: id
        description: id of the metric
      - in: query
        name: provider_key
        description: Your api key with 3scale (also known as provider key)
      - in: path
        name: service_id
        description: id of the service
      - in: query
        name: unit
        description: Measure unit of the metric
      responses:
        200:
          description: OK
      tags:
      - Metric
  /stats/applications/{application_id}/usage.{format}:
    get:
      summary: Application Usage by Metric
      description: Application usage by metric.
      operationId: application_ops
      x-api-path-slug: statsapplicationsapplication-idusage-format-get
      parameters:
      - in: path
        name: application_id
        description: id of the application
      - in: path
        name: format
        description: Response format
      - in: query
        name: granularity
        description: Granularity of the results
      - in: query
        name: metric_name
        description: System name of metric for which to get data
      - in: query
        name: period
        description: 'Period, combined with since give the stats for the time range
          [since '
      - in: query
        name: provider_key
        description: Your api key with 3scale
      - in: query
        name: since
        description: Time range start
      - in: query
        name: skip_change
        description: Skip period over period calculations (setting this to true will
          increase the performance of the call)
      - in: query
        name: timezone
        description: Timezone to do the calculations in
      - in: query
        name: until
        description: Time range end
      responses:
        200:
          description: OK
      tags:
      - Application
      - Usage
      - By
      - Metric
  /stats/services/{service_id}/usage.{format}:
    get:
      summary: Service Usage by Metric
      description: Service usage by metric.
      operationId: service_ops
      x-api-path-slug: statsservicesservice-idusage-format-get
      parameters:
      - in: path
        name: format
        description: Response format
      - in: query
        name: granularity
        description: Granularity of the results
      - in: query
        name: metric_name
        description: System name of metric for which to get data
      - in: query
        name: period
        description: 'Period, combined with since give the stats for the time range
          [since '
      - in: query
        name: provider_key
        description: Your api key with 3scale
      - in: path
        name: service_id
        description: id of the service
      - in: query
        name: since
        description: Time range start
      - in: query
        name: skip_change
        description: Skip period over period calculations (setting this to true will
          increase the performance of the call)
      - in: query
        name: timezone
        description: Timezone to do the calculations in
      - in: query
        name: until
        description: Time range end
      responses:
        200:
          description: OK
      tags:
      - Service
      - Usage
      - By
      - Metric
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---