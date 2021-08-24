# Loki

[Loki](https://github.com/grafana/loki/)

This setup uses the new boltdb-shipper shipped with Loki 2.0.0.


## Components:

  - compactor: (optional) BoltDB Shipper specific service [docs](https://github.com/grafana/loki/blob/master/docs/sources/operations/storage/boltdb-shipper.md#compactor)
  - distributor: validates incoming logs and sends to ingester
  - index-gateway: synchronizes the BoltDB index from the Object Storage in order to serve index queries to the Queriers and Rulers over gRPC
  - ingester: writes logs to backing store
  - query-frontend: (optional) [info](https://github.com/grafana/loki/blob/master/docs/sources/architecture/_index.md#query-frontend)
  - querier: performs the queries
  - ruler: alerting [info](https://grafana.com/docs/loki/latest/rules/)
    This application includes a sidecar that picks up rules from kubernetes `ConfigMap` with the label `loki_rule` set.
  - table-manager: (not used)
