# Loki

Log collection and searching using [Loki](https://github.com/grafana/loki/) with [Promtail](https://github.com/grafana/loki/tree/master/docs/clients/promtail).

This setup uses the new boltdb-shipper shipped with Loki 2.0.0.


## Components:

  - compactor: (optional) BoltDB Shipper specific service [docs](https://github.com/grafana/loki/blob/master/docs/sources/operations/storage/boltdb-shipper.md#compactor)
  - distributor: validates incoming logs and sends to ingester
  - ingester: writes logs to backing store
  - query-frontend: (optional) [info](https://github.com/grafana/loki/blob/master/docs/sources/architecture/_index.md#query-frontend)
  - querier: performs the queries
  - table-manager: (not used)
