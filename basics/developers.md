---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-08-23"

keywords: developer, getting started, command line interface, cli

subcollection: cloud-object-storage

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:important: .important}
{:note: .note}
{:download: .download} 

# For developers of {{site.data.keyword.cos_full_notm}}
{: #gs-dev}

The powerful tools of {{site.data.keyword.cos_full}} are available to a developer directly from the command line.
{: .shortdesc}

First, ensure that you have the [{{site.data.keyword.cloud}} Platform CLI](https://cloud.ibm.com/docs/cli/index.html) and [IBM Developer Tools](https://cloud.ibm.com/docs/cloudnative/idt/index.html) installed.

## Create an instance of {{site.data.keyword.cos_full_notm}}
{: #gs-dev-provision}

  1. First, make sure that you have an API key. Get it from [IBM Cloud Identity and Access Management](https://cloud.ibm.com/iam/apikeys).
  2. Log in to {{site.data.keyword.cloud_notm}} Platform by using the CLI. It's also possible to store the API key in a file or set it as an environment variable.

```
ibmcloud login --apikey <value>
```
{: codeblock}

  3. Next, create an instance of {{site.data.keyword.cos_full_notm}} specifying the name for the instance, the ID, and the wanted plan (lite or standard). Now we have a CRN for the instance. If you have an upgraded account, specify the `Standard` plan. Otherwise, specify `Lite`.

```
ibmcloud resource service-instance-create <instance-name> cloud-object-storage <plan> global
```
{: codeblock}

The [Getting Started guide](/docs/services/cloud-object-storage?topic=cloud-object-storage-getting-started) walks through the basic steps of creating buckets and objects, as well as inviting users and creating policies. A list of basic 'curl' commands can be found [here](/docs/services/cloud-object-storage/cli?topic=cloud-object-storage-curl).

Learn more about using the {{site.data.keyword.cloud_notm}} CLI to create applications, manage Kubernetes clusters, and more [in the documentation](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli).


## Using the API
{: #gs-dev-api}

For managing data stored in {{site.data.keyword.cos_short}}, you can use S3 API compatible tools like the [AWS CLI](/docs/services/cloud-object-storage/cli?topic=cloud-object-storage-aws-cli)with [HMAC credentials](/docs/services/cloud-object-storage/hmac?topic=cloud-object-storage-hmac) for compatibility. As IAM tokens are relatively easy to work with, `curl` is a good choice for basic testing and interaction with your storage. More information can be found in [the `curl` reference](/docs/services/cloud-object-storage/cli?topic=cloud-object-storage-curl), as well as [the API reference documentation](/docs/services/cloud-object-storage/api-reference?topic=cloud-object-storage-compatibility-api).

## Using libraries and SDKs
{: #gs-dev-sdk}
IBM COS SDKs are available for [Python](/docs/services/cloud-object-storage/libraries?topic=cloud-object-storage-python), [Java](/docs/services/cloud-object-storage/libraries?topic=cloud-object-storage-java), [Go](/docs/services/cloud-object-storage/libraries?topic=cloud-object-storage-go), and [Node.js](/docs/services/cloud-object-storage/libraries?topic=cloud-object-storage-node). These libraries are forked and modified versions of the AWS S3 SDKs that support [IAM token-based authentication](/docs/services/cloud-object-storage/iam?topic=cloud-object-storage-iam-overview), as well as support for [Key Protect](/docs/services/cloud-object-storage/basics?topic=cloud-object-storage-encryption). 

## Building applications on IBM Cloud
{: #gs-dev-apps}
{{site.data.keyword.cloud}} provides flexibility to developers in choosing the right architectural and deployment options for a given application. Run your code on [bare metal](https://cloud.ibm.com/catalog/infrastructure/bare-metal), in [virtual machines](https://cloud.ibm.com/catalog/infrastructure/virtual-server-group), by using a [serverless framework](https://cloud.ibm.com/openwhisk), in [containers](https://cloud.ibm.com/kubernetes/catalog/cluster), or by using [Cloud Foundry](https://cloud.ibm.com/catalog/starters/sdk-for-nodejs). 

The [Cloud Native Computing Foundation](https://www.cncf.io) fostered [Kubernetes](https://kubernetes.io) container orchestration framework, which forms the foundation for the {{site.data.keyword.cloud}} Kubernetes Service. Developers who want to use Object Storage for persistent storage in their Kubernetes applications can learn more at the following links:

 * [Choosing a storage solution](/docs/containers?topic=containers-storage_planning#choose_storage_solution)
 * [Comparison table for persistent storage options](/docs/containers?topic=containers-storage_planning#persistent_storage_overview)
 * [Main COS page](/docs/containers?topic=containers-object_storage)
 * [Installing COS](/docs/containers?topic=containers-object_storage#install_cos)
 * [Creating COS service instance](/docs/containers?topic=containers-object_storage#create_cos_service)
 * [Creating COS secret](/docs/containers?topic=containers-object_storage#create_cos_secret)
 * [Decide on the configuration](/docs/containers?topic=containers-object_storage#configure_cos)
 * [Create an instance of COS](/docs/containers?topic=containers-object_storage#add_cos)
 * [Back up and restore information](/docs/containers?topic=containers-object_storage#backup_restore)
 * [Storage Class reference](/docs/containers?topic=containers-object_storage#storageclass_reference)


