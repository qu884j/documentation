---
title: Datadog-Desk Integration
integration_title: Desk
kind: integration
git_integration_title: desk
---
## Overview

Connect Desk to Datadog to:

  * Receive new case events in the event stream
  * Visualize case stats by user and status
  * View trends in support tickets alongside DevOps issues

## Configuration

From your Desk account, add an API application on the Settings -> API -> My Applications page (you made need administrator privileges.
Fill out the form as shown, leaving the latter two URL fields blank. Desk should then generate an application key, application secret, API access token, and API access token secret.

{{< img src="integrations/desk/desk_config.png" alt="desk config" >}}

Then from your Datadog account, enter the corresponding information on the [Desk tile][1]. You will also need to enter your company's unique Desk domain name.
Hit the install button, and then you're all set! You will soon be able to select desk.* metrics on a custom dashboard or view them on the provided [Desk dashboard][2]. (You can also read about this integration on [our blog][3].)

## Metrics

{{< get-metrics-from-git >}}

[1]: https://app.datadoghq.com/account/settings#integrations/desk
[2]: https://app.datadoghq.com/screen/integration/desk
[3]: https://www.datadoghq.com/blog/keep-support-team-page-salesforce-desk-integration/