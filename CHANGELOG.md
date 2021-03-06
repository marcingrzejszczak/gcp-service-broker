# Change Log
All releases of the GCP Service Broker will be documented in
this file. This project adheres to [Semantic Versioning](http://semver.org/).

## [1.0.0] - 2016-10-03

### Fixed
- Switched from using PLANS environment variable to using CLOUDSQL_CUSTOM_PLANS 
to generate CloudSQL plans. Fixed bug where at least one CloudSQL plan was required
and changed DB password type in tile config from string to secret. Note that due to
a migration issue in Ops Manager, you'll need to delete and re-install the broker 
if you are using it as a tile.

## [1.0.1] - 2016-10-07

### Fixed
- Removed specified stemcell version from tile.yml so that most recent stemcell is 
used by default.

## [2.0.0] - 2016-10-10

### Fixed
- fixed CloudSQL docs link in README
- updated credentials type returned by bind call to be a map[string]string instead
of a string.

## [2.0.1] - 2016-10-28

- CloudSQL will generate a username/password on bind if one is not provided.

### Fixed
- CloudSQL custom plans are now optional
- fixed username and password env var names in docs
- fixed CloudSQL custom plan names and/or features not updating

## [2.0.2] - 2016-11-16

### Fixed
- fixed bug where CloudSQL was returning 400s for all 2nd gen instance provision requests

## [2.1.0] - 2016-12-02

- Remove need for service name for PubSub (topic_name), BigQuery (name), Cloud Storage (name), and Cloud SQL (instance_name)
- Instance details are now surfaced in bind requests for Pubsub (topic_name and subscription_name),
Cloud Storage (bucket_name), BigQuery (dataset_id), and Cloud SQL (instance_name, database_name, and host)

## [2.1.1] - 2016-12-02

- added new uri parameter to Cloud SQL bind credentials

## [2.1.2] - 2016-12-21

- fixes a bug where anything that triggered an install repeat after installing version 2.1.0 or 2.1.1 would cause the
installation to fail.

## [2.1.3] - 2017-01-05

- fixes a bug where bind calls to ml-api service instances were failing because these service instances don't save
any extra access details
