# Developer Dashboards

This folder contains a modified form of the following Grafana dashboards:
* [Mattermost Performance Monitoring](https://grafana.com/grafana/dashboards/2542)
* [Mattermost Performance Monitoring (Bonus Metrics)](https://grafana.com/grafana/dashboards/2545)
* [Mattermost Performance KPI Metrics](https://grafana.com/grafana/dashboards/2539)

The dashboards are modified from the version available on grafana.com since [Grafana doesn't currently support variables](https://github.com/grafana/grafana/issues/10786) (i.e. `${DS_MATTERMOST}`) and has no way of binding the datasource with the dashboards at the time of provisioning. Instead of falling back to the REST API to effect these changes, the following in-place changes were made to the exported dashboards available above:
* Remove the top-level `__inputs` key
* Remove the top-level `__requires` key
* Replace all instances of `${DS_MATTERMOST}` with `Prometheus`, matching the name of the provisioned datasource.

The process above will need to be repeated in the event newer versions of these dashboards are published.
