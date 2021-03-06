# Changelog

All notable changes to this project will be documented in this file.

## [0.6.1] - 2018-09-27
* Bug fixes

## [0.6.0] - 2018-09-26
* Support for Service Accounts and deploying from CI/CD pipelines
* Fixed ingress redirect issue
* Updated to Alpine 3.8 for all images including Airflow
* New automated build pipeline

## [0.5.1] - 2018-09-13
* Support for upgrading individual airflow deployments to latest chart.
* Fix for airflow task logs link on taskinstances page.

## [0.5.0] - 2018-09-10
* Support for the KubernetesPodOperator. Every deployment goes into its own namespace with resource quotas, limits and defaults.
* Support node auto-scaling. All containers are now assigned resource requests/limits.
* Support for database connection pooling. pgbouncer is now deployed with every deployment to pool connections to postgres for all airflow pods (webserver/scheduler/workers/kubepodoperators/etc)
* Grafana enhancements. New pgbouncer and nginx dashboards, fixed some queries (smooth out container metric graphs), and added deployment dropdowns to all dashboards to drill down into specific deployments.
* Fixed worker logs garbage collector
* Faster deploys. Fixed containers from restarting on initial boot, especially noticeable with flower.
* Larger default volume size for workers/prometheus/registry.
* Updated NGINX ingress controller.
* Some new options and configurations in the airflow chart (choosing executor, horizontal pod autoscaling, connection pooling, etc) that will make their way into the deployment configuration in the future.
* Other minor bug fixes and backend enhancements

## [0.4.1] - 2018-08-17
* Added local email/password authentication option
* Integration with Auth0
* Default installation can now use local, Google, or Github as auth providers
* Fixed some Airflow webserver stability issues with a better healthcheck
* Fixed Grafana healthcheck
* Updated Grafana to v5.2.2
* Removed unused Prometheus target
* Larger default volume size on airflow workers

## [0.3.2] - 2018-07-29

* Prevent redis and flower from restarting during deployments.
* All charts protected with NetworkPolicies.
* Improved docker caching, resulting in faster development and faster deployments.

## [0.2.1] - 2018-05-17

* Added nginx-auth secret to houston, fixing issue with airflow deploys being created unsecured

## [0.2.0] - 2018-05-08

* Set astronomer to be the only chart to install by default
* Updated houston chart to save global values as an env
* Updated commander chart to have elevated tiller permissions
* Updated all chart to include version in the chart label

## [0.1.4] - 2018-04-03

* Upgrade setuptools in Airflow image

## [0.1.3] - 2018-03-21

* Replace Phoenix with Houston

## [0.1.2] - 2018-03-01

* Add /healthz to default backend

## [0.1.1] - 2018-02-28

* Add platform default backend

## [0.1.0] - 2018-02-26

* Initial public release

## [0.0.34] - 2018-02-24

* Add relabelling rules to prometheus and updated metric names in grafana dashboard.

## [0.0.30] - 2018-02-21

* Added nginx image.
* Removed basic auth via env from registry in favor of nginx.

## [0.0.27] - 2018-02-04

* Bump commander and phoenix. Adds support for private docker registry.

## [0.0.23] - 2018-02-03

* Entrypoint script for docker registry.

## [0.0.22] - 2018-02-03

* Added Module/Component labels.
* Fixed phoenix image.

## [0.0.19] - 2018-02-02

* Added Registry.

## [0.0.18] - 2018-02-01

* Added Commander.
* Added Phoenix.

## [0.0.17] - 2018-01-26

* Added labels for open.

## [0.0.16] - 2018-01-12

* Changed Airflow worker-gc environment variable name.

## [0.0.15] - 2018-01-10

* Added support for clearing worker logs after x days.
* Removed Snakebite python package due to compatibility issues with python 3.

## [0.0.14] - 2018-01-08

* Fixed busted grafana build.

## [0.0.13] - 2018-01-07

* Added support for passing default prometheus host for grafana datasource.

## [0.0.12] - 2018-01-07

* Changed Prometheus config file name and paths.

## [0.0.11] - 2018-01-05

* Added Prometheus Marathon config.

## [0.0.10] - 2018-01-04

* Added Python and pip symlinks to python3 and pip3.
* Removed usage of .astro directory in start script.

## [0.0.9] - 2018-01-04

* Added vendor images.

## [0.0.8] - 2018-01-03

* Added Tini init system.

## [0.0.5] - 2017-12-15

* Added support for Airflow onbuild tags.

## [0.0.4] - 2017-12-15

* Added this Changelog
* Added StatsD package to Airflow
* Added StatsD exporter to stack.
* Added Prometheus to stack.
* Added Grafana to stack.
* Airflow scripts now run docker-compose with -d flag.
