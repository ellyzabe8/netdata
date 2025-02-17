<!--startmeta
custom_edit_url: "https://github.com/netdata/netdata/edit/master/collectors/freebsd.plugin/integrations/net.inet6.ip6.stats.md"
meta_yaml: "https://github.com/netdata/netdata/edit/master/collectors/freebsd.plugin/metadata.yaml"
sidebar_label: "net.inet6.ip6.stats"
learn_status: "Published"
learn_rel_path: "Data Collection/FreeBSD"
message: "DO NOT EDIT THIS FILE DIRECTLY, IT IS GENERATED BY THE COLLECTOR'S metadata.yaml FILE"
endmeta-->

# net.inet6.ip6.stats

Plugin: freebsd.plugin
Module: net.inet6.ip6.stats

<img src="https://img.shields.io/badge/maintained%20by-Netdata-%2300ab44" />

## Overview

Collect information abou IPv6 stats.

The plugin calls `sysctl` function to collect necessary data.

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



### Per net.inet6.ip6.stats instance

These metrics show general information about IPv6 connections.

This scope has no labels.

Metrics:

| Metric | Dimensions | Unit |
|:------|:----------|:----|
| ipv6.packets | received, sent, forwarded, delivers | packets/s |
| ipv6.fragsout | ok, failed, all | packets/s |
| ipv6.fragsin | ok, failed, timeout, all | packets/s |
| ipv6.errors | InDiscards, OutDiscards, InHdrErrors, InAddrErrors, InTruncatedPkts, InNoRoutes, OutNoRoutes | packets/s |



## Alerts

There are no alerts configured by default for this integration.


## Setup

### Prerequisites

No action required.

### Configuration

#### File

The configuration file name for this integration is `netdata.conf`.
Configuration for this specific integration is located in the `[plugin:freebsd:net.inet6.ip6.stats]` section within that file.

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
| ipv6 packets | Enable or disable ipv6 packet metric. |  | False |
| ipv6 fragments sent | Enable or disable ipv6 fragments sent metric. |  | False |
| ipv6 fragments assembly | Enable or disable ipv6 fragments assembly metric. |  | False |
| ipv6 errors | Enable or disable ipv6 errors metric. |  | False |

</details>

#### Examples
There are no configuration examples.


