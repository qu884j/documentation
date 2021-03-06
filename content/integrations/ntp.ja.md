---
integration_title: NTP Check
kind: integration
newhlevel: true
placeholder: true
title: Datadog-NTP Check Integration
---

<div class='alert alert-info'><strong>NOTICE:</strong>アクセスいただきありがとうございます。こちらのページは現在英語のみのご用意となっております。引き続き日本語化の範囲を広げてまいりますので、皆様のご理解のほどよろしくお願いいたします。</div>



## Overview

{{< img src="integrations/ntp/ntpgraph.png" alt="NTP Graph" >}}

The Network Time Protocol (NTP) integration is enabled by default and reports the time offset from an ntp server every 15 minutes. When the local agent's time is more than 15 seconds off from the Datadog service and the other hosts that you are monitoring, you may experience:

* Incorrect alert triggers
* Metric delays
* Gaps in graphs of metrics

For more information on syncing your system clock with NTP, [see this article in the Datadog Knowledge Base](https://help.datadoghq.com/hc/en-us/articles/204282095-Network-Time-Protocol-NTP-Offset-Issues)

## Installation

No installation steps are required for this integration.

## Configuration

1.  The ntp check is enabled by default. If you would like to make any changes to the configuration, move `ntp.yaml.default` to `ntp.yaml` and edit:
{{< highlight yaml>}}
init_config:

instances:
  - offset_threshold: 60
{{< /highlight >}}

2. Restart the agent

### Configuration Options

* `host` (Optional) - Host name of alternate ntp server, for example `pool.ntp.org`
* `port` (Optional) - What port to use
* `version` (Optional) - ntp version
* `timeout` (Optional) - Response timeout

## Validation

To validate your installation and configuration, restart the agent and execute the info command. The output should contain a section similar to the following:
{{< highlight shell>}}
Checks
======
  [...]
  ntp
  -----
      - instance #0 [OK]
      - Collected 1 metric & 0 events
{{< /highlight >}}
## Usage

## Metrics

{{< get-metrics-from-git "system" "ntp" >}}

## Events

No events are included with this integration.
