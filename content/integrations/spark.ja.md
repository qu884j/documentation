---
doclevel: basic
git_integration_title: spark
integration_title: Spark
kind: integration
newhlevel: true
placeholder: true
title: Datadog-Spark Integration
---

<div class='alert alert-info'><strong>NOTICE:</strong>アクセスいただきありがとうございます。こちらのページは現在英語のみのご用意となっております。引き続き日本語化の範囲を広げてまいりますので、皆様のご理解のほどよろしくお願いいたします。</div>




## Overview

Get metrics from your app in real time to

  * Visualize performance metrics

{{< img src="integrations/spark/sparkgraph.png" alt="spark graph" >}}

## Configuration

*Install Datadog Agent on the Master Node where the ResourceManager is running*

1.  Configure the agent to connect to the ResourceManager. Edit `conf.d/spark.yaml`

        init_config:

        instances:
          #
          # The Spark check retrieves metrics from YARN's ResourceManager. This
          # check must be run from the Master Node and the ResourceManager URI must
          # be specified below. The ResourceManager URI is composed of the
          # ResourceManager's hostname and port.
          #
          # The ResourceManager hostname can be found in the yarn-site.xml conf file
          # under the property yarn.resourcemanager.address
          #
          # The ResourceManager port can be found in the yarn-site.xml conf file under
          # the property yarn.resourcemanager.webapp.address
          #
          - resourcemanager_uri: http://localhost:8088

          # An optional friendly name can be specified for the cluster.
          #   cluster_name: MySparkCluster

            # Additional tags can be specified for the metrics.
            # tags:
            #   - optional_tag1
            #   - optional_tag2

{{< insert-example-links >}}

## Validation

1.  Restart the Agent
2.  Execute the info command and verify that the integration check passed. The output of the command should contain a section similar to the following:


        Checks
        ======

          [...]

          spark
          -----
            - instance #0 [OK]
            - Collected 0 metrics, 0 events & 2 service checks

## Metrics

{{< get-metrics-from-git >}}
