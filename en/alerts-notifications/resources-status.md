---
id: resources-status
title: Resources Status
---

The `Monitoring > Resources Status` page is your main view to track
resources events & statuses, analyze & quickly handle them.

This view mixes hosts & services to have a unified interface and way to manage
events.

## Events list

The event list is a condensed and efficient view of all alerts or resource status
monitored by Centreon.

![image](../assets/alerts/resources-status/resources-status-listing.png)

It's possible to add, remove and sort by the column of your choice.

![image](../assets/alerts/resources-status/resources-status-listing-order.gif)

## Take actions on events

### Acknowledge an event

When one or more alerts are visible, you may need to acknowledge them to tell
your team that the problem is handled, you can do that in two ways:

-   By directly acknowledging the line, an "Acknowledgement" button
    appears on mouseover
-   By selecting multiple lines and clicking on the "Acknowledgement"
    button, above the table

You can also disacknowledge previously acknowledged events by choosing the
"Disacknowledge" action in the "More actions" menu.

![image](../assets/alerts/resources-status/resources-status-acknowledgement.gif)

> Only "non-ok" resources can be acknowledged and you cannot acknowledge a resource already acknowledged

When a resource is acknowledged, the alert is not visible anymore in the
"Unhandled problems" filter and notifications for this resource are stopped.
The color of the line for acknowledged resources is changed
to yellow.

The acknowledgement can also be deleted, in which case the event will be included again in the Unhandled Problems and its notifications will resume.

### Set a planned downtime

When a maintenance is planned on one or multiple resources, you can set a
planned downtime for them in Centreon in two ways:

-   By directly setting a planned downtime on the line,
    a "Set Downtime" button appears on mouseover
-   By selecting multiple lines and clicking on the "Downtime" button,
    above the table

![image](../assets/alerts/resources-status/resources-status-downtime.gif)

When a resource is in planned downtime, the alert is not visible anymore in the
"Unhandled problems" filter and notifications for this resource are stopped. The
color of lines for resources with a planned downtime is changed to light purple.

### Refresh a status

In many situations, you need to quickly re-check one or multiple services
to refresh their status. This can be achieved in two ways:

-   By directly clicking on the "Check" button on the line when the
    mouse is over
-   By selecting multiple lines and clicking on the "Check" button,
    above the table

![image](../assets/alerts/resources-status/resources-status-check.gif)

### Submit a status

In some cases, especially with so-called "passive" services, it can be useful
to submit a result, i.e. a status, an output and metrics, in order to
reset the event.
This can be achieved using the "Submit Status" action, available when a single passive service is selected.

![image](../assets/alerts/resources-status/resources-status-submit-status.gif)

## Filter

### Pre-defined filters

When you open the Resource status page, the default filter is "Unhandled
problems". This filter quickly shows all problems/alerts that are not yet
handled so you can focus on choosing the most relevant alerts to take
care of. You can choose two other filters that are "Resources problems"
and "All".

The following rules apply:

-   Unhandled problems: resource status is Warning or Critical or
    Unknown or Down AND the resource is not acknowledged nor in planned
    downtime
-   Resource problems: resource status is Warning or Critical or Unknown
    or Down
-   All: All resources

![image](../assets/alerts/resources-status/resources-status-filters-defaults.gif)

### Search bar

It's possible to filter out the events by name of resources. You can use
the power of regular expression mechanism to finely search for resources
(host or services)

By default, the search bar will look for your expression to match with:

-   Host name
-   Host alias
-   Address or FQDN
-   Service description
-   Information

![image](../assets/alerts/resources-status/resources-status-search-simple.png)

It's possible to force search on specific fields by using the following
labels:

-   h.name: only search in the host name field
-   h.alias: only search in host alias field
-   h.address: only search in the host address field
-   s.description: only search in the service description field
-   information: only search in the information field

![image](../assets/alerts/resources-status/resources-status-search-label.png)

### By advanced criteria

If pre-defined filter and the search bar are not enough, it's possible
to expand the filter bar to access the following additionnal criteria:

-   Resource types (host, service or meta-service)
-   Statuses (Ok, Warning, Critical, Unknown, Pending, Up, Down)
-   States: Is the problem already acknowledged, in a planned downtime
    or simply unhandled
-   Host groups
-   Service groups
-   Monitoring server: monitoring server (or poller) to which the resources are attached

You can use the **[+]** button on the left to select the set of criteria displayed.

![image](../assets/alerts/resources-status/resources-status-search-advanced.gif)


### Save your filter

You may create some "complex" filters that set you in a specific
context, using multiple criteria and even complex regular expressions.
In that case, you may want to save this filter and re-use it later.

This is possible using the **gear icon** next to Filter. You'll be able to:

-   Save your current search as a new filter
-   Save the current filter so that it is updated using your current
    applied criterias
-   Edit filters so that you can rename, re-order or delete them

As soon as a filter is saved, it's re-usable in the Filter dropdown list,
categorized under "My Filter".

![image](../assets/alerts/resources-status/resources-status-filters-custom.gif)

By clicking on the "Edit filters" menu, you can manage your existing filters (rename, re-order and delete):

![image](../assets/alerts/resources-status/resources-status-edit-filters.gif)

## Detail panel

When you click on a line, a detail panel opens on the right side to display main information
concerning the resource.

The panel is extendable to the left up to 85% of your page width with its content responding to the changes in available space.

Depending on the type of resource, the detail panel displays different information.

### Host panel

The host panel contains several informative tabs:

-   Detailed information about its current status,
-   A listing of its attached services and their current status (as well as their graphs if the corresponding mode is selected),
-   The timeline of events that occurred for this host,
-   Shortcuts to the configuration, logs and report.

![image](../assets/alerts/resources-status/resources-status-panel-host.gif)

If an acknowledgement or downtime is set on the host, it will be displayed in
the panel and the header will be accordingly colored.

### Service panel

The service panel contains several informative tabs:

-   Detailed information about its current status,
-   The timeline of events that occured for this service,
-   A graph with one curve per metric collected by this service,
-   Shortcuts to the configurations, logs and reports for this service and its
    related host.

![image](../assets/alerts/resources-status/resources-status-panel-service.gif)

If an acknowledgement or downtime is set on the service, it will be displayed in
the panel and the header will be accordingly colored.

#### Graph

The graph tab enables you to visually display how the metrics evolve for the selected resource. 

Hovering over the metric curves will display under the graph's title the precise time and also display within the legend the different values for that same point in time.

When the pointer is not hovering over curves, the legend displays Min, Max and Average values for each metric.

![image](../assets/alerts/resources-status/resources-status-graph-values-in-legend.gif)

It's possible to select or deselect metrics to display using the legend. By clicking on a legend item, it will unselect all metrics other than this one. Clicking on a metric being the only one selected will select all of them:

![image](../assets/alerts/resources-status/resources-status-graph-select-only-metric.gif)

You can also toggle the selection of individual metrics by Ctrl+Clicking (or Cmd+Clicking for Mac users) on the corresponding tile within the legend:

![image](../assets/alerts/resources-status/resources-status-graph-toggle-legends.gif)

Graphs display metric evolution over a given period of time. This can be defined in the following ways:
- A selection of preconfigured periods is available in the graph header: 

    [Last Day | Last 7 Days | Last 31 Days]
- Datetime pickers are available for Start and End points in time. Anytime the displayed period changes, this element is updated accordingly
- Using the side [<] and [>] buttons that appear upon hovering the graph's border, you can translate in time by half your current timespan (respectively backward and forward in time)
- Selecting a period of time within the graph will zoom in on this period

![image](../assets/alerts/resources-status/resources-status-graph-time-selection.gif)


The "Display events" toggle (available under the **gear** button) allows you to display some timeline events (Downtime, Acknowledgement, Comment) directly on the graph, via annotations:

![image](../assets/alerts/resources-status/resources-status-graph-display-events.gif)

It is possible to add a comment directly on the graph, by left clicking anywhere at the time you want to add it, and select "Add a comment" on the tooltip that appears:

![image](../assets/alerts/resources-status/resources-status-graph-add-comment.gif)

By clicking on the "Export to PNG" button, you can export a snapshot of the graph, which also includes the timeline events, if the switch is toggled. Note that only the selected metrics will be exported:

![image](../assets/alerts/resources-status/resources-status-graph-export-to-png.gif)
