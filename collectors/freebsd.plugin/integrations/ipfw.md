<!--startmeta
custom_edit_url: "https://github.com/netdata/netdata/edit/master/collectors/freebsd.plugin/integrations/ipfw.md"
meta_yaml: "https://github.com/netdata/netdata/edit/master/collectors/freebsd.plugin/metadata.yaml"
sidebar_label: "ipfw"
learn_status: "Published"
learn_rel_path: "Data Collection/FreeBSD"
message: "DO NOT EDIT THIS FILE DIRECTLY, IT IS GENERATED BY THE COLLECTOR'S metadata.yaml FILE"
endmeta-->

# ipfw

Plugin: freebsd.plugin
Module: ipfw

<img src="https://img.shields.io/badge/maintained%20by-Netdata-%2300ab44" />

## Overview

Collect information about FreeBSD firewall.

The plugin uses RAW socket to communicate with kernel and collect data.

This collector is supported on all platforms.

This collector supports collecting metrics from multiple instances of this integration, including remote instances.


### Default Behavior

#### Auto-Detection

This integration doesn't support auto-detection.

#### Limits

The default configuration for this integration does not impose any limits on data collection.

#### Performance Impact

The default configuration for this integration is not expected to impose a significant performance impact on the system.


## Metrics

Metrics grouped by *scope*.

The scope defines the instance that the metric belongs to. An instance is uniquely identified by a set of labels.



### Per ipfw instance

Theese metrics show FreeBSD firewall statistics.

This scope has no labels.

Metrics:

| Metric | Dimensions | Unit |
|:------|:----------|:----|
| ipfw.mem | dynamic, static | bytes |
| ipfw.packets | a dimension per static rule | packets/s |
| ipfw.bytes | a dimension per static rule | bytes/s |
| ipfw.active | a dimension per dynamic rule | rules |
| ipfw.expired | a dimension per dynamic rule | rules |



## Alerts

There are no alerts configured by default for this integration.


## Setup

### Prerequisites

No action required.

### Configuration

#### File

The configuration file name for this integration is `netdata.conf`.
Configuration for this specific integration is located in the `[plugin:freebsd:ipfw]` section within that file.

The file format is a modified INI syntax. The general structure is:

```toml
[section1]
    option 1 = some value
    option 2 = some other value

[section2]
    option 3 = some third value
```
You can edit the configuration file using the `edit-config` script from the
Netdata [config directory](https://github.com/netdata/netdata/blob/master/docs/configure/nodes.md#the-netdata-config-directory).

```bash
cd /etc/netdata 2>/dev/null || cd /opt/netdata/etc/netdata
sudo ./edit-config netdata.conf
```
#### Options



<details><summary>Config options</summary>

| Name | Description | Default | Required |
|:----|:-----------|:-------|:--------:|
| counters for static rules | Enable or disable counters for static rules  metric. |  | False |
| number of dynamic rules | Enable or disable number of dynamic rules metric. |  | False |
| allocated memory | Enable or disable allocated memory metric. |  | False |

</details>

#### Examples
There are no configuration examples.


