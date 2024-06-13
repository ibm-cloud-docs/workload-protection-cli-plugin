---

copyright:
  years:  2022
lastupdated: "2022-06-20"

subcollection: sysdig-secure-plugin-cli

keywords:  CLI,  command line ,  terminal, shell, compliance

---

{{site.data.keyword.attribute-definition-list}}


# Compliance (ibmcloud sysdig-secure compliance) CLI
{: #sysdig-secure-compliance-cli}

The {{site.data.keyword.sysdigsecure_full}} compliance CLI lets you determine the available frameworks, platforms, and scope options as well as create and manage benchmark and compliance tasks.
{: shortdesc}


## Concepts
{: #sysdig-secure-concepts}

To use this CLI you will need to understand the following {{site.data.keyword.sysdigsecure_full_notm}} concepts. For more information on {{site.data.keyword.sysdigsecure_full_notm}}, see the [{{site.data.keyword.sysdigsecure_full_notm}} documentation.](/docs/workload-protection?topic=workload-protection-getting-started)

* Compliance frameworks provide guidelines and structures to maintain security and help meet regulatory requirements.

* Compliance platforms include the available platforms to be monitored including platforms such as Kubernetes, Docker, and so on.

* Scope options are the available scope labels and operators that can be used when creating a benchmark or compliance task.

* Tasks are benchmark or compliance tasks ...

## Command options
{: #ss_compliance_options}

The following are the available options for all `ibmcloud sysdig-secure compliance` commands.

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

## ibmcloud sysdig-secure compliance frameworks
{: #ss_compliance_frameworks}

This command returns a list of available frameworks in your {{site.data.keyword.sysdigsecure_full_notm}} instance.

```sh
ibmcloud sysdig-secure compliance frameworks (--instance-id INSTANCE_ID | --instance-name INSTANCE_NAME) [--region REGION] [--output FORMAT] [--quiet]
```
{: pre}

### Frameworks command options
{: #ss_compliance_frameworks_options}

See the [command options](#ss_compliance_options) for a description of each option.

## ibmcloud sysdig-secure compliance platforms
{: #ss_compliance_platforms}

This command returns a list of available platforms in your {{site.data.keyword.sysdigsecure_full_notm}} instance.

```sh
ibmcloud sysdig-secure compliance platforms (--instance-id INSTANCE_ID | --instance-name INSTANCE_NAME) [--region REGION] [--output FORMAT] [--quiet]
```
{: pre}

### Platforms command options
{: #ss_compliance_platforms_options}

See the [command options](#ss_compliance_options) for a description of each option.

## ibmcloud sysdig-secure compliance scope-options
{: #ss_compliance_scopeoptions}

This command returns a list of available scope options in your {{site.data.keyword.sysdigsecure_full_notm}} instance.

```sh
ibmcloud sysdig-secure compliance scope options --framework FRAMEWORK --platform PLATFORM [--version VERSION] (--instance-id INSTANCE_ID | --instance-name INSTANCE_NAME) [--region REGION] [--output FORMAT] [--quiet]
```
{: pre}

### Compliance scope-options command options
{: #ss_compliance_scopeoptions_options}

`--framework`
:   The name of a framework in your {{site.data.keyword.sysdigsecure_full_notm}} instance. Available frameworks can be found using the [`ibmcloud sysdig-secure compliance frameworks` command.](#ss_compliance_frameworks)

`--platform`
:   The name of a platform in your {{site.data.keyword.sysdigsecure_full_notm}} instance. Available platforms can be found using the [`ibmcloud sysdig-secure compliance platforms` command.](#ss_compliance_platforms)

`--version`
:   You can optionally specify the version of the framework.

See the [command options](#ss_compliance_options) for a description of additional options.

## ibmcloud sysdig-secure compliance task control-counts
{: #ss_compliance_controlcounts}

This command returns the control counts for a compliance task in your {{site.data.keyword.sysdigsecure_full_notm}} instance.

```sh
ibmcloud sysdig-secure compliance task --id ID (--instance-id INSTANCE_ID | --instance-name INSTANCE_NAME) [--region REGION] [--output FORMAT] [--quiet]
```
{: pre}

### Compliance task control-counts command options
{: #ss_compliance_controlcount_options}

`--id`
:   The task ID of the compliance task.  You can find a list of configured tasks by running the [`ibmcloud sysdig-secure compliance task list` command.](#ss_compliance_tasklist)

See the [command options](#ss_compliance_options) for a description of additional options.

## ibmcloud sysdig-secure compliance task create
{: #ss_compliance_taskcreate}

This command creates a new compliance task in your {{site.data.keyword.sysdigsecure_full_notm}} instance.

WIP: The following command example needs to be reworked when we have a better understanding as to which options are optional and required. Initial help does not match the listed options.
{: important}

```sh
ibmcloud sysdig-secure compliance task create (--instance-id INSTANCE_ID | --instance-name INSTANCE_NAME) [--region REGION] [--output FORMAT] [--quiet]
```
{: pre}

### Compliance task create command options
{: #ss_compliance_taskcreate_options}

`--enabled`
:   Indicates if the task is enabled, and can be run, or is disabled. Default is `false` indicating that the task is not enabled.

`--excludeControlList`
:   List of control IDs to be excluded.

`--framework`
:   The name of a framework in your {{site.data.keyword.sysdigsecure_full_notm}} instance. Available frameworks can be found using the [`ibmcloud sysdig-secure compliance frameworks` command.](#ss_compliance_frameworks)

`--name`
:   The name to be given to the task.

`--platform`
:   The name of a platform in your {{site.data.keyword.sysdigsecure_full_notm}} instance. Available platforms can be found using the [`ibmcloud sysdig-secure compliance platforms` command.](#ss_compliance_platforms)

`--schedule`
:   The schedule when the task will be run.

`--schema`
:   The benchmark or compliance schema to be applied to the task.

`--scope`
:   The task scope.

`--version`
:   You can optionally specify the version of the framework.


See the [command options](#ss_compliance_options) for a description of additional options.

## ibmcloud sysdig-secure compliance task delete
{: #ss_compliance_taskdelete}

This command deletes a task defined in your {{site.data.keyword.sysdigsecure_full_notm}} instance.

```sh
ibmcloud sysdig-secure compliance task delete [--id ID] (--instance-id INSTANCE_ID | --instance-name INSTANCE_NAME) [--region REGION] [--output FORMAT] [--quiet]
```
{: pre}

### Compliance task delete command options
{: #ss_compliance_taskdelete_options}

`--id`
:   The task ID of the compliance task.  You can find a list of configured tasks by running the [`ibmcloud sysdig-secure compliance task list` command.](#ss_compliance_tasklist)

See the [command options](#ss_compliance_options) for a description of additional options.

## ibmcloud sysdig-secure compliance task disable
{: #ss_compliance_taskdisable}

This command disables a task defined in your {{site.data.keyword.sysdigsecure_full_notm}} instance. A disabled task cannot be run.

```sh
ibmcloud sysdig-secure compliance task disable [--id ID] (--instance-id INSTANCE_ID | --instance-name INSTANCE_NAME) [--region REGION] [--output FORMAT] [--quiet]
```
{: pre}

### Compliance task disable command options
{: #ss_compliance_taskdisable_options}

`--id`
:   The task ID of the compliance task.  You can find a list of configured tasks by running the [`ibmcloud sysdig-secure compliance task list` command.](#ss_compliance_tasklist)

See the [command options](#ss_compliance_options) for a description of additional options.

## ibmcloud sysdig-secure compliance task enable
{: #ss_compliance_taskenable}

This command enables a task defined in your {{site.data.keyword.sysdigsecure_full_notm}} instance. An enabled task can be run.  Disabled tasks cannot be run.

```sh
ibmcloud sysdig-secure compliance task enable [--id ID] (--instance-id INSTANCE_ID | --instance-name INSTANCE_NAME) [--region REGION] [--output FORMAT] [--quiet]
```
{: pre}

### Compliance task enable command options
{: #ss_compliance_taskenable_options}

`--id`
:   The task ID of the compliance task.  You can find a list of configured tasks by running the [`ibmcloud sysdig-secure compliance task list` command.](#ss_compliance_tasklist)

See the [command options](#ss_compliance_options) for a description of additional options.

## ibmcloud sysdig-secure compliance task latest-report
{: #ss_compliance_tasklatestreport}

This command returns the latest report for the task defined in your {{site.data.keyword.sysdigsecure_full_notm}} instance.

```sh
ibmcloud sysdig-secure compliance task latest-report [--id ID] (--instance-id INSTANCE_ID | --instance-name INSTANCE_NAME) [--region REGION] [--output FORMAT] [--quiet]
```
{: pre}

### Compliance task latest-report command options
{: #ss_compliance_tasklatestreport_options}

`--id`
:   The task ID of the compliance task.  You can find a list of configured tasks by running the [`ibmcloud sysdig-secure compliance task list` command.](#ss_compliance_tasklist)

See the [command options](#ss_compliance_options) for a description of additional options.

## ibmcloud sysdig-secure compliance task list
{: #ss_compliance_tasklist}

This command lists the tasks defined in your {{site.data.keyword.sysdigsecure_full_notm}} instance.

```sh
ibmcloud sysdig-secure compliance task list [--framework FRAMEWORK] [--platform PLATFORM] [--version VERSION] [--filter FILTER] (--instance-id INSTANCE_ID | --instance-name INSTANCE_NAME) [--region REGION] [--output FORMAT] [--quiet]
```
{: pre}

### Compliance task list command options
{: #ss_compliance_tasklist_options}


`--filter`
:   TBD

`--framework`
:   The name of a framework in your {{site.data.keyword.sysdigsecure_full_notm}} instance. Available frameworks can be found using the [`ibmcloud sysdig-secure compliance frameworks` command.](#ss_compliance_frameworks)

`--platform`
:   The name of a platform in your {{site.data.keyword.sysdigsecure_full_notm}} instance. Available platforms can be found using the [`ibmcloud sysdig-secure compliance platforms` command.](#ss_compliance_platforms)

`--version`
:   You can optionally specify the version of the framework.


See the [command options](#ss_compliance_options) for a description of additional options.

## ibmcloud sysdig-secure compliance task report
{: #ss_compliance_taskreport}

This command returns the latest report for the task defined in your {{site.data.keyword.sysdigsecure_full_notm}} instance.

```sh
ibmcloud sysdig-secure compliance task report [--id ID] [--report-id] (--instance-id INSTANCE_ID | --instance-name INSTANCE_NAME) [--region REGION] [--output FORMAT] [--quiet]
```
{: pre}

### Compliance task report command options
{: #ss_compliance_tasktreport_options}

`--id`
:   The task ID of the compliance task.  You can find a list of configured tasks by running the [`ibmcloud sysdig-secure compliance task list` command.](#ss_compliance_tasklist)

`--report-id`
:   The report ID.

See the [command options](#ss_compliance_options) for a description of additional options.

## ibmcloud sysdig-secure compliance task run
{: #ss_compliance_taskrun}

This command runs a task defined in your {{site.data.keyword.sysdigsecure_full_notm}} instance.

```sh
ibmcloud sysdig-secure compliance task run [--id ID] [--is-test IsTest] (--instance-id INSTANCE_ID | --instance-name INSTANCE_NAME) [--region REGION] [--output FORMAT] [--quiet]
```
{: pre}

### Compliance task report command options
{: #ss_compliance_tasktreport_options}

`--id`
:   The task ID of the compliance task.  You can find a list of configured tasks by running the [`ibmcloud sysdig-secure compliance task list` command.](#ss_compliance_tasklist)

`--is-test IsTest`
:   If specified the task is run in test mode. (???)

See the [command options](#ss_compliance_options) for a description of additional options.
