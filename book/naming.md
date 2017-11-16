# Naming

## Precision and Context

> Why? With a growing codebase the single most important thing for maintainability is to quickly understand what's happening. Names that are not absolutely precise or don't take future developments into account will significantly increase the cognitive load for anybody working with the application.

#### Situation

* `tracking-db` A database with tracking events running on Google BigQuery
* `tracking-pixel`A service with an HTTP endpoint that persists events to the tracking-db
* `tracking-analyzer` A service that queries tracking-db to count and meter the number of tracking events

#### Question: How to name a metric created by tracking-analyzer

##### First Solution

* Name:`tracking_events_total`
* Description: "The number of tracking events in BigQuery"

##### Problems

* The name is too generic, if tracking-pixel also meters incoming events, they conflict
* The description refers to a specific platform/technology. "BigQuery" is used interchangeably with `tracking-db`.
  That's okay until
  * The database technology is changed \(this should not affect the description of metrics\)
  * Other data is stored in BigQuery \(be it other services or the tracking-pixel/tracking-analyzer\)

##### Better Solution

* Name:`tracking_events_in_database_total`
* Description: "The number of tracking events found in the tracking-db"



