---

copyright:
  years:  2022
lastupdated: "2022-06-07"

subcollection: sysdig-secure-plugin-cli

keywords: CLI, command line, terminal, shell

---

{{site.data.keyword.attribute-definition-list}}


# {{site.data.keyword.sysdigsecure_short}} (ibmcloud sysdig-secure) CLI
{: #sysdig-secure-cli}

The {{site.data.keyword.cloud}} command-line interface (CLI) provides extra capabilities for service offerings. This information describes how you can use the CLI to access information in {{site.data.keyword.sysdigsecure_full_notm}}.
{: shortdesc}

## Prerequisites
{: #sysdig-secure-cli-prereq}

* Install the [{{site.data.keyword.cloud_notm}} CLI](/docs/cli?topic=cli-getting-started).
* Install the {{site.data.keyword.sysdigsecure_full_notm}} CLI by running the following command:

   ```sh
   ibmcloud plugin install sysdig-secure
   ```
   {: pre}

You are notified on the command line when updates to the {{site.data.keyword.cloud_notm}} CLI and plug-ins are available. Be sure to keep your CLI up to date so that you can use the latest commands. You can view the current version of all installed plug-ins by running `ibmcloud plugin list`.
{: tip}

## Available CLIs
{: #sysdig-secure-cli-types}

{{site.data.keyword.sysdigsecure_full_notm}} provides two CLIs:

[Compliance](/docs/workload-protection-cli-plugin?topic=workload-protection-cli-plugin-sysdig-secure-compliance-cli)
:   The compliance CLI lets you determine the available frameworks, platforms, and scope options as well as create and manage benchmark and compliance tasks.

[Policy](/docs/workload-protection-cli-plugin?topic=workload-protection-cli-plugin-sysdig-secure-policy-cli)
:   The policy CLI lets you create and manage compliance policies.
