<!--startmeta
custom_edit_url: "https://github.com/netdata/netdata/edit/master/collectors/cgroups.plugin/integrations/kubernetes_containers.md"
meta_yaml: "https://github.com/netdata/netdata/edit/master/collectors/cgroups.plugin/metadata.yaml"
sidebar_label: "Kubernetes Containers"
learn_status: "Published"
learn_rel_path: "Data Collection/Kubernetes"
message: "DO NOT EDIT THIS FILE DIRECTLY, IT IS GENERATED BY THE COLLECTOR'S metadata.yaml FILE"
endmeta-->

# Kubernetes Containers

Plugin: cgroups.plugin
Module: /sys/fs/cgroup

<img src="https://img.shields.io/badge/maintained%20by-Netdata-%2300ab44" />

## Overview

Monitor Containers for performance, resource usage, and health status.



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



### Per k8s cgroup



Labels:

| Label      | Description     |
|:-----------|:----------------|
| k8s_namespace | TBD |
| k8s_pod_name | TBD |
| k8s_pod_uid | TBD |
| k8s_controller_kind | TBD |
| k8s_controller_name | TBD |
| k8s_node_name | TBD |
| k8s_container_name | TBD |
| k8s_container_id | TBD |
| k8s_kind | TBD |
| k8s_qos_class | TBD |
| k8s_cluster_id | TBD |

Metrics:

| Metric | Dimensions | Unit |
|:------|:----------|:----|
| k8s.cgroup.cpu_limit | used | percentage |
| k8s.cgroup.cpu | user, system | percentage |
| k8s.cgroup.cpu_per_core | a dimension per core | percentage |
| k8s.cgroup.throttled | throttled | percentage |
| k8s.cgroup.throttled_duration | duration | ms |
| k8s.cgroup.cpu_shares | shares | shares |
| k8s.cgroup.mem | cache, rss, swap, rss_huge, mapped_file | MiB |
| k8s.cgroup.writeback | dirty, writeback | MiB |
| k8s.cgroup.mem_activity | in, out | MiB/s |
| k8s.cgroup.pgfaults | pgfault, swap | MiB/s |
| k8s.cgroup.mem_usage | ram, swap | MiB |
| k8s.cgroup.mem_usage_limit | available, used | MiB |
| k8s.cgroup.mem_utilization | utilization | percentage |
| k8s.cgroup.mem_failcnt | failures | count |
| k8s.cgroup.io | read, write | KiB/s |
| k8s.cgroup.serviced_ops | read, write | operations/s |
| k8s.cgroup.throttle_io | read, write | KiB/s |
| k8s.cgroup.throttle_serviced_ops | read, write | operations/s |
| k8s.cgroup.queued_ops | read, write | operations |
| k8s.cgroup.merged_ops | read, write | operations/s |
| k8s.cgroup.cpu_some_pressure | some10, some60, some300 | percentage |
| k8s.cgroup.cpu_some_pressure_stall_time | time | ms |
| k8s.cgroup.cpu_full_pressure | some10, some60, some300 | percentage |
| k8s.cgroup.cpu_full_pressure_stall_time | time | ms |
| k8s.cgroup.memory_some_pressure | some10, some60, some300 | percentage |
| k8s.cgroup.memory_some_pressure_stall_time | time | ms |
| k8s.cgroup.memory_full_pressure | some10, some60, some300 | percentage |
| k8s.cgroup.memory_full_pressure_stall_time | time | ms |
| k8s.cgroup.io_some_pressure | some10, some60, some300 | percentage |
| k8s.cgroup.io_some_pressure_stall_time | time | ms |
| k8s.cgroup.io_full_pressure | some10, some60, some300 | percentage |
| k8s.cgroup.io_full_pressure_stall_time | time | ms |

### Per k8s cgroup network device



Labels:

| Label      | Description     |
|:-----------|:----------------|
| device | TBD |
| interface_type | TBD |
| k8s_namespace | TBD |
| k8s_pod_name | TBD |
| k8s_pod_uid | TBD |
| k8s_controller_kind | TBD |
| k8s_controller_name | TBD |
| k8s_node_name | TBD |
| k8s_container_name | TBD |
| k8s_container_id | TBD |
| k8s_kind | TBD |
| k8s_qos_class | TBD |
| k8s_cluster_id | TBD |

Metrics:

| Metric | Dimensions | Unit |
|:------|:----------|:----|
| k8s.cgroup.net_net | received, sent | kilobits/s |
| k8s.cgroup.net_packets | received, sent, multicast | pps |
| k8s.cgroup.net_errors | inbound, outbound | errors/s |
| k8s.cgroup.net_drops | inbound, outbound | errors/s |
| k8s.cgroup.net_fifo | receive, transmit | errors/s |
| k8s.cgroup.net_compressed | receive, sent | pps |
| k8s.cgroup.net_events | frames, collisions, carrier | events/s |
| k8s.cgroup.net_operstate | up, down, notpresent, lowerlayerdown, testing, dormant, unknown | state |
| k8s.cgroup.net_carrier | up, down | state |
| k8s.cgroup.net_mtu | mtu | octets |



## Alerts


The following alerts are available:

| Alert name  | On metric | Description |
|:------------|:----------|:------------|
| [ k8s_cgroup_10min_cpu_usage ](https://github.com/netdata/netdata/blob/master/health/health.d/cgroups.conf) | k8s.cgroup.cpu_limit | average cgroup CPU utilization over the last 10 minutes |
| [ k8s_cgroup_ram_in_use ](https://github.com/netdata/netdata/blob/master/health/health.d/cgroups.conf) | k8s.cgroup.mem_usage | cgroup memory utilization |
| [ k8s_cgroup_1m_received_packets_rate ](https://github.com/netdata/netdata/blob/master/health/health.d/cgroups.conf) | k8s.cgroup.net_packets | average number of packets received by the network interface ${label:device} over the last minute |
| [ k8s_cgroup_10s_received_packets_storm ](https://github.com/netdata/netdata/blob/master/health/health.d/cgroups.conf) | k8s.cgroup.net_packets | ratio of average number of received packets for the network interface ${label:device} over the last 10 seconds, compared to the rate over the last minute |


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


