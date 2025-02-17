<!--startmeta
custom_edit_url: "https://github.com/netdata/netdata/edit/master/collectors/proc.plugin/integrations/zfs_pools.md"
meta_yaml: "https://github.com/netdata/netdata/edit/master/collectors/proc.plugin/metadata.yaml"
sidebar_label: "ZFS Pools"
learn_status: "Published"
learn_rel_path: "Data Collection/Linux Systems/Filesystem/ZFS"
message: "DO NOT EDIT THIS FILE DIRECTLY, IT IS GENERATED BY THE COLLECTOR'S metadata.yaml FILE"
endmeta-->

# ZFS Pools

Plugin: proc.plugin
Module: /proc/spl/kstat/zfs

<img src="https://img.shields.io/badge/maintained%20by-Netdata-%2300ab44" />

## Overview

This integration provides metrics about the state of ZFS pools.



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



### Per zfs pool



Labels:

| Label      | Description     |
|:-----------|:----------------|
| pool | TBD |

Metrics:

| Metric | Dimensions | Unit |
|:------|:----------|:----|
| zfspool.state | online, degraded, faulted, offline, removed, unavail, suspended | boolean |



## Alerts


The following alerts are available:

| Alert name  | On metric | Description |
|:------------|:----------|:------------|
| [ zfs_pool_state_warn ](https://github.com/netdata/netdata/blob/master/health/health.d/zfs.conf) | zfspool.state | ZFS pool ${label:pool} state is degraded |
| [ zfs_pool_state_crit ](https://github.com/netdata/netdata/blob/master/health/health.d/zfs.conf) | zfspool.state | ZFS pool ${label:pool} state is faulted or unavail |


## Setup

### Prerequisites

No action required.

### Configuration

#### File

There is no configuration file.
#### Options



There are no configuration options.

#### Examples
There are no configuration examples.


