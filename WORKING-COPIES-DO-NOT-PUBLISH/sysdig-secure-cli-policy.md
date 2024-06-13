---

copyright:
  years:  2022
lastupdated: "2022-06-20"

subcollection: sysdig-secure-plugin-cli

keywords: CLI, command line, terminal, shell, policy

---

{{site.data.keyword.attribute-definition-list}}


# Policy (ibmcloud sysdig-secure policy) CLI
{: #sysdig-secure-policy-cli}

The {{site.data.keyword.sysdigsecure_full}} policy CLI lets you create and manage compliance policies.
{: shortdesc}


## Concepts
{: #sysdig-secure-policy concepts}

To use this CLI you will need to understand the following {{site.data.keyword.sysdigsecure_full_notm}} concepts. For more information on {{site.data.keyword.sysdigsecure_full_notm}}, see the [{{site.data.keyword.sysdigsecure_full_notm}} documentation.](/docs/workload-protection?topic=workload-protection-getting-started)

* You can configure a policy on a resource and define what to do when 1 or more rules that are included in the policy are non-compliant.

* {{site.data.keyword.sysdigsecure_full_notm}} includes a number of pre-defined policies that you can use.

## Command options
{: #ss_policy_options}

The following are the available options for all `ibmcloud sysdig-secure policy` commands.

`--instance-id` (required), exclusive with `--instance-name`
:   The ID of the {{site.data.keyword.sysdigsecure_full_notm}} instance. The ID can be obtained by running the [`ibmcloud resource service-instance` command.](/docs/cli?topic=cli-ibmcloud_commands_resource#ibmcloud_resource_service_instance) One of `--instance-id` or `--instance-name` must be specified. The `--instance-id` and `--instance-name` options cannot be specified together on the same command invocation.

`--instance-name` (required), exclusive with `--instance-id`
:   The name of the {{site.data.keyword.sysdigsecure_full_notm}} instance.  This is the [name](/docs/workload-protection?topic=workload-protection-provision) you specified when creating the instance. One of `--instance-id` or `--instance-name` must be specified. The
`--instance-id` and `--instance-name` options cannot be specified together on the same command invocation.

`--region REGION` | `-r REGION`
:   Name of the region, for example, `us-south` or `eu-gb`. If not specified, the region logged into, or targeted, will be used.

`--output FORMAT`
:   Available output formats are `JSON`, `YAML`, or `TABLE`.  If not specified, output will be returned in a tabular format.

`--quiet` | `-q`
:   Suppress verbose messages.

`help` | `--help` | `-h`
:   List options available for the command.

## ibmcloud sysdig-secure policy create
{: #ss_policy_create}

This command creates a security policy for your {{site.data.keyword.sysdigsecure_full_notm}} instance.

```sh
ibmcloud sysdig-secure policy create (--file FILE | --json JSON) (--instance-id INSTANCE_ID | --instance-name INSTANCE_NAME) [--region REGION] [--output FORMAT] [--quiet]
```
{: pre}

### Policy create command options
{: #ss_policy_create_options}

WIP: We need the definition of the JSON that needs to be passed on this command or in the file.
{: important}

`--file`
:   A file containing the policy definition in JSON format.

`--json`
:   The policy definition in JSON format.

See the [command options](#ss_policy_options) for a description of additional options.

## ibmcloud sysdig-secure policy defaults
{: #ss_policy_defaults}

WIP: Missing information: How are default policies created?  When are they used?
{: important}

This command returns the default policies created for your {{site.data.keyword.sysdigsecure_full_notm}} instance.

```sh
ibmcloud sysdig-secure policy defaults (--instance-id INSTANCE_ID | --instance-name INSTANCE_NAME) [--region REGION] [--output FORMAT] [--quiet]
```
{: pre}

### Policy defaults command options
{: #ss_policy_defaults_options}

See the [command options](#ss_policy_options) for a description of additional options.

## ibmcloud sysdig-secure policy delete
{: #ss_policy_delete}

This command deletes a security policy in your {{site.data.keyword.sysdigsecure_full_notm}} instance.

```sh
ibmcloud sysdig-secure policy delete --id ID (--instance-id INSTANCE_ID | --instance-name INSTANCE_NAME) [--region REGION] [--output FORMAT] [--quiet]
```
{: pre}

### Policy delete command options
{: #ss_policy_delete_options}

`--id`
:   The policy ID of the policy.  You can find a list of policies by running the [`ibmcloud sysdig-secure policy list` command.](#ss_policy_list)

See the [command options](#ss_policy_options) for a description of additional options.

## ibmcloud sysdig-secure policy get
{: #ss_policy_get}

This command returns a security policy in your {{site.data.keyword.sysdigsecure_full_notm}} instance.

```sh
ibmcloud sysdig-secure policy get --id ID (--instance-id INSTANCE_ID | --instance-name INSTANCE_NAME) [--region REGION] [--output FORMAT] [--quiet]
```
{: pre}

### Policy get command options
{: #ss_policy_get_options}

`--id`
:   The policy ID of the policy.  You can find a list of policies by running the [`ibmcloud sysdig-secure policy list` command.](#ss_policy_list)

See the [command options](#ss_policy_options) for a description of additional options.

## ibmcloud sysdig-secure policy list
{: #ss_policy_list}

WIP: Missing information: What exactly is returned by running the list command?  How do you filter (filter string format). What are offset and severity and how are they used (and what are valid values).
{: important}

This command lists the security policies defined for your {{site.data.keyword.sysdigsecure_full_notm}} instance.

```sh
ibmcloud sysdig-secure policy list [--filter FILTER] [--limit LIMIT] [--offset OFFSET] [--severity SEVERITY] (--instance-id INSTANCE_ID | --instance-name INSTANCE_NAME) [--region REGION] [--output FORMAT] [--quiet]
```
{: pre}

### Policy get command options
{: #ss_policy_get_options}

`--filter`
:   Filters the list of policies returned by the specified criteria.

`--limit`
:   Limits the number of policies returned. This is a value between `1` and `100`. If not specified, a maximum of 100 policies are returned.

`--offset`
:   **NEED DEFINITION AND USAGE**

`--severity`
:   **NEED DEFINITION AND USAGE**


See the [command options](#ss_policy_options) for a description of additional options.

## ibmcloud sysdig-secure policy update
{: #ss_policy_update}

This command updates an existing security policy for your {{site.data.keyword.sysdigsecure_full_notm}} instance.

```sh
ibmcloud sysdig-secure policy update --ID ID (--file FILE | --json JSON) (--instance-id INSTANCE_ID | --instance-name INSTANCE_NAME) [--region REGION] [--output FORMAT] [--quiet]
```
{: pre}

### Policy create command options
{: #ss_policy_create_options}

WIP: We need the definition of the JSON that needs to be passed on this command or in the file.  Also, is this a complete update (all values replaced) or only those specified in the JSON. In other words, does the the entire policy definition need to be submitted on the update command?
{: important}

`--file`
:   A file containing the policy definition in JSON format.

`--id`
:   The policy ID of the policy.  You can find a list of policies by running the [`ibmcloud sysdig-secure policy list` command.](#ss_policy_list)

`--json`
:   The policy definition in JSON format.

See the [command options](#ss_policy_options) for a description of additional options.
