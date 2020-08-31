---


copyright:
  years: 2016, 2020
lastupdated: "2020-08-31"

keywords: console, platform overview, overview, data center, security, compliance

subcollection: overview

---

{:shortdesc: .shortdesc}
{:external: target="_blank" .external}

# What is the {{site.data.keyword.Bluemix_notm}} platform?
{: #whatis-platform}

The {{site.data.keyword.IBM}} cloud platform combines platform as a service (PaaS) with infrastructure as a service (IaaS) to provide an integrated experience. The platform scales and supports both small development teams and organizations, and large enterprise businesses. Globally deployed across data centers around the world, the solution you build on {{site.data.keyword.cloud}} spins up fast and performs reliably in a tested and supported environment you can trust.
{: .shortdesc}

The platform is built to support your needs whether it's working only in the public cloud or taking advantage of a multicloud deployment model. With our open-source technologies, such as Kubernetes, Red Hat OpenShift, and a full range of compute options, including virtual machines, containers, bare metal, and serverless, you have as much control and flexibility as you need to support workloads in your hybrid environment. You can deploy cloud-native apps while also ensuring workload portability.

Whether you need to migrate apps to the cloud, modernize your existing apps by using cloud services, ensure data resiliency against regional failure, or leverage new paradigms and deployment topologies to innovate and build your cloud-native apps, the platform's open architecture is built to accommodate your use case.

## What's built into the platform?

As the following diagram illustrates, the {{site.data.keyword.Bluemix_notm}} platform is composed of multiple components that work together to provide a consistent and dependable cloud experience. 

  * A robust console that serves as the front end for creating, viewing, managing your cloud resources
  * An identity and access management component that securely authenticates users for both platform services and controls access to resources consistently across {{site.data.keyword.Bluemix_notm}}
  * A catalog that consists of hundreds of supported products 
  * A search and tagging mechanism for filtering and identifying your resources
  * An account and billing management system that provides exact usage for pricing plans and secure credit card fraud protection
  
![Components of the {{site.data.keyword.cloud_notm}} platform.](images/IBM-Cloud-Platform.svg "Diagram showiing the major components of the {{site.data.keyword.cloud_notm}} platform"){: caption="Figure 1. Components of the {{site.data.keyword.cloud_notm}} platform" caption-side="bottom"}

Whether you have [existing code](/docs/apps?topic=apps-tutorial-byoc#tutorial-byoc) that you want to modernize and bring to the cloud or you're developing a [brand new application](/docs/apps?topic=apps-tutorial-starterkit), your developers can tap into the rapidly growing ecosystem of available services and runtime frameworks in {{site.data.keyword.Bluemix_notm}}.

## Setting up your account
{: #set-up-account}

If you're a developer and you're just trying out {{site.data.keyword.Bluemix_notm}}, you can go straight to the catalog and browse the products that you'd like to explore and add to your Lite account. When you're ready to get started with an environment and get apps running in production, consider setting up the basics in your account:

* User access groups for organizing users and service IDs into one entity to make assigning access a streamlined process.
* Resource groups for organizing your resources to make assigning access to a set of resources quick and easy.
* Access policies for your access groups or individual developers who need IAM access policies or Cloud Foundry org and space roles.

For more information, see the [best practices for organizing your resources and assigning access](/docs/account?topic=account-account_setup).

As a financial officer for your company, you might be interested in simplifying how you manage billing and usage across multiple teams and departments. With a Subscription account, you can create an {{site.data.keyword.Bluemix_notm}} enterprise, which offers centralized account management, consolidated billing, and top-down usage reporting. An enterprise consists of an enterprise account, account groups, and individual accounts. 

* The enterprise account is the parent account to all other accounts in the enterprise. Billing for the entire enterprise is managed at the enterprise account level.
* Account groups provide a way to organize related accounts. And, you get a unified view of resource usage costs across all accounts that are included in an account group.
* Similar to stand-alone accounts, accounts in an enterprise contain resources and resource groups, Cloud Foundry orgs and spaces, and independent access permissions.

For more information, see the [best practices for setting up an enterprise](/docs/account?topic=account-enterprise-best-practices).

## {{site.data.keyword.Bluemix_notm}} catalog
{: #catalog}

{{site.data.keyword.Bluemix_notm}} provides a full-stack, public cloud platform with a variety of products in the catalog, including compute, storage, and networking options, end-to-end developer solutions for app development, testing and deployment, security management services, traditional and open-source databases, and cloud-native services. You can find all of these services on the Services tab in the catalog. The lifecycle and operations of these services are the responsibility of {{site.data.keyword.IBM_notm}}.

The Software tab includes a growing catalog of software products, including [Cloud Paks](https://www.youtube.com/watch?v=DzFhhSR8SSs){: external}, [starter kits](/docs/apps?topic=apps-starter-kits), Terraform-based templates, and [Helm charts](https://www.ibm.com/cloud/blog/announcements/bitnami-application-catalog-now-available-within-ibm-cloud){: external}. Even though you're responsible for the lifecycle management, deployment, and configuration of these software products on your own compute resources, you can take advantage of a simplified installation process that helps you to get up and running quickly.

The catalog supports command-line interfaces (CLIs) and a RESTful API for users to retrieve information about existing products, and create, manage, and delete their resources. 

### Searching the catalog 
{: #catalog-filter-options}

The following table lists the filter options you can use when searching the catalog. 

| Option      | Description  |
|------------------|-------|
| AI / Machine Learning | Products that enable systems to learn from data rather than through explicit programming. |
| Analytics | Products that facilitate the analysis of data, typically large sets of business data, by the use of mathematics, statistics, and other means. |
| Blockchain | Products that facilitate the process of recording transactions and tracking assets in a business network. |
| Compute | Infrastructure resources that serve as the basis for building apps in the cloud. |
| Containers | A standard unit of software that packages up code and all its dependencies so the app runs quickly and reliably from one computing environment to another. |
| Databases | Products that provide some form of access to a database without the need for setting up physical hardware, installing software, or configuring for performance. |
| Developer Tools | Products that support developing, testing, and debugging software. |
| Integration | Products that facilitate the connection of data, apps, APIs, and devices across an organization to be more efficient, productive, and agile. |
| Internet of Things | Products that support receiving and transferring data over wireless networks without human intervention. |
| Logging and Monitoring | Products that support storing, searching, analyzing, and monitoring log data and events. And, products that support reviewing and managing the operational workflow and processes being logged. |
| Mobile | Products with specific or special utility for users creatings things to be used on mobile devices. |
| Networking | Products that support or augment the linking of computers so they can operate interactively. |
| Security | Products that provide the protection of stored data from theft, leakage, and deletion. |
| Storage  | Products that support data to be created, read, updated, and deleted. |
{: caption="Table 1. Options for filtering by category" caption-side="top"}
{: #category-svc}
{: tab-title="Category"}
{: tab-group="cfo"}
{: class="simple-tab-table"}
{: summary="Use the buttons before the table to change the context of the table. The column headers identify the options for fitering based on filter type."}

| Option | Description |
|--------------|-------|
| {{site.data.keyword.IBM_notm}} | The lifecycle and operations of the service are the responsibility of {{site.data.keyword.IBM_notm}}. |
| Third party | Support for the service is the responsibility of the third-party provider. If the root cause analysis determines that the issue is a defect in the service, {{site.data.keyword.IBM_notm}} isn't required to provide a fix. However, {{site.data.keyword.IBM_notm}} shares analysis with the third-party provider, if needed, and can work with the third-party provider to help solve the issue. |
{: caption="Table 1. Options for filtering by provider" caption-side="top"}
{: #provider-svc}
{: tab-title="Provider"}
{: tab-group="cfo"}
{: class="simple-tab-table"}
{: summary="Use the buttons before the table to change the context of the table. The column headers identify the options for fitering based on filter type."} 

| Option | Description |
|--------------|-------|
| Free | The service includes monthly free allowances. |
| Lite | The pricing plan for the service is structured as a free quota. The quota might operate for a specific time period, for example, a month or on a one-off usage basis. |
{: caption="Table 1. Options for filtering by pricing plan" caption-side="top"}
{: #pricingplan-svc}
{: tab-title="Pricing plan"}
{: tab-group="cfo"}
{: class="simple-tab-table"}
{: summary="Use the buttons before the table to change the context of the table. The column headers identify the options for fitering based on filter type."} 

| Option | Description |
|--------------|-------|
| EU Supported | Support for the service is specifically provided by {{site.data.keyword.cloud_notm}} support team members located in the European Union (EU) region. |
| HIPAA Enabled | The service is designated as HIPAA ready, meaning processing, storing, and handling Protected Health Information (PHI) in the service is supported. |
| IAM-enabled | The service is enabled to use {{site.data.keyword.cloud_notm}} Identity and Access Management (IAM) for access control. Access policies are used to assign users and service IDs access to specific resources in an account.|
| Service Endpoint Supported | The service can be connected to over the {{site.data.keyword.cloud_notm}} private network instead of the public network. Connecting directly to service endpoints doesn't require internet access, providing increased security. |
{: caption="Table 1. Options for filtering by compliance" caption-side="top"}
{: #compliance-svc}
{: tab-title="Compliance"}
{: tab-group="cfo"}
{: class="simple-tab-table"}
{: summary="Use the buttons before the table to change the context of the table. The column headers identify the options for fitering based on filter type."}

| Option | Description |
|--------------|-------|
| Beta | The service is available for evaluation and testing purposes. Beta services aren't intended for production use. |
| Deprecated | The service is supported but no longer recommended and might become obsolete. |
{: caption="Table 1. Options for filtering by release" caption-side="top"}
{: #release-svc}
{: tab-title="Release"}
{: tab-group="cfo"}
{: class="simple-tab-table"}
{: summary="Use the buttons before the table to change the context of the table. The column headers identify the options for fitering based on filter type."}

## Pricing and billing
{: #pricing-billing}

When you're choosing a service from the catalog and you select a tile, if there are different types of available plans you can find pricing details. If you choose a service plan with a paid plan, you can estimate your costs by using the cost estimator tool. For more information, see [Estimating your costs](/docs/billing-usage?topic=billing-usage-cost). 

{{site.data.keyword.Bluemix_notm}} billing provides multiple services that ensure the {{site.data.keyword.Bluemix_notm}} platform can securely manage pricing, accounts, usage, and more.

### Account management
{: #account-mgmt}

Account management maintains the billing relationship with the customer. Each account is a billing entity that represents a customer. This service controls account lifecycle, subscription, user relationship, and organization.

### Pricing
{: #pricing}

The pricing platform service helps you to define, manage, and retrieve pricing information for resources in the {{site.data.keyword.Bluemix_notm}} catalog.

### Usage metering
{: #metering}

With usage metering, service providers can submit metrics that are collected for resource instances that are provisioned by {{site.data.keyword.Bluemix_notm}} users. Third-party service providers that deliver an integrated billing service are required to submit usage for all active service instances every hour. 

### Usage reports
{: #usage}

Usage reports return the summary for the account for the specified month. Account billing managers are authorized to access the reports.

## Creating resources
{: #provisioning-layer}

The resource controller is the next-generation {{site.data.keyword.Bluemix_notm}} platform provisioning layer that manages the lifecycle of {{site.data.keyword.Bluemix_notm}} resources in your account. Resources are provisioned globally in an account scope. The resource controller supports both synchronous and asynchronous provisioning of resources. Examples of resources include databases, accounts, processors, memory, and storage limits. 

In general, resources that are tracked by the provisioning layer are intended to associate usage metrics and billing, but that isn’t always the case. In some cases, the resource might be associated with the provisioning layer to ensure that the resource lifecycle can be managed along with the account lifecycle. The resource controller uses {{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM) for authentication and authorization of actions that are taken against the provisioning layer.

### Resource lifecycle management
{: #lifecycle}

The resource controller provides common APIs to control the lifecycle of resources from creating an instance to creating access credentials to removing access to deleting an instance.

## Managing your resources
{: #resource-manager}

A collection of resources is managed by [resource groups](/docs/account?topic=account-rgs). A resource group is associated with your account. All {{site.data.keyword.Bluemix_notm}} resources must be assigned to a resource group. When you create an account, a default resource group is created for you. All {{site.data.keyword.Bluemix_notm}} IAM-enabled resources must be provisioned within a resource group. If you have a Lite account, you can have only one resource group. If you have a Pay-As-You-Go or Subscription account, you can create more than one resource group. If an account is suspended, the corresponding resource group is suspended as well, and all resources within the resource group are suspended. 

## Searching and tagging resources
{: #search-and-tag}

The search service is a global and shared resource properties repository that is integrated within the {{site.data.keyword.Bluemix_notm}} platform. It is used for storing and searching a cloud resource's attributes, and it categorizes and classifies resources. Resources are uniquely identified by a [Cloud Resource Name (CRN)](/docs/account?topic=account-crn) identifier. The properties of a resource include tags and system properties. Both properties are defined within an {{site.data.keyword.Bluemix_notm}} billing account, and span across many regions.

This service also manages tags that are associated with a resource. You can create, delete, search, attach, or detach tags with the Tagging API. Tags are uniquely identified by a CRN identifier. Tags have a name, which must be unique within a billing account. You can create tags in key:value pairs or label format.

## Managing security and compliance
{: #account-security-compliance}

The {{site.data.keyword.compliance_full}} offers a single location where you can validate that your resources are meeting continuous security and compliance.

With the {{site.data.keyword.compliance_short}}, you can create profiles and config rules to ensure that specific areas of your business adhere to your defined requirements or industry regulations. From the {{site.data.keyword.compliance_short}} dashboard, you can download detailed reports that you can use to provide evidence to stakeholders or external auditors. The {{site.data.keyword.compliance_short}} also offers security insights that you can use to detect potential threats when observing your account activity. For more information, see [Getting started with {{site.data.keyword.compliance_short}}](/docs/security-compliance?topic=security-compliance-getting-started). 

## Monitoring your resources
{: #resources_observability}

Observability offers a single location where you can monitor and observe your applications and services in {{site.data.keyword.Bluemix_notm}}. 

With the {{site.data.keyword.la_full}} service, you can add log management capabilities to your {{site.data.keyword.Bluemix_notm}} architecture and you can manage system and application logs. It offers advanced features to monitor and troubleshoot, define alerts, and design custom dashboards. {{site.data.keyword.la_full_notm}} is operated by LogDNA in partnership with {{site.data.keyword.IBM_notm}}. For more information, see [Getting started with {{site.data.keyword.la_full_notm}}](/docs/Log-Analysis-with-LogDNA?topic=Log-Analysis-with-LogDNA-getting-started).

The {{site.data.keyword.mon_full_notm}} service, allows you to gain operational visibility into the performance and health of your applications, services, and platforms. It offers a full stack telemetry with advanced features to monitor and troubleshoot, define alerts, and design custom dashboards. {{site.data.keyword.mon_full_notm}} is operated by Sysdig in partnership with {{site.data.keyword.IBM_notm}}. For more information, see [Getting started with IBM Cloud Monitoring with Sysdig service](/docs/Monitoring-with-Sysdig?topic=Monitoring-with-Sysdig-getting-started#getting-started).

## Monitoring your account 
{: #account_observability}

Use the {{site.data.keyword.at_full}} service to monitor the activity of your {{site.data.keyword.Bluemix_notm}} account, investigate abnormal activity and critical actions, and comply with regulatory audit requirements. In addition, you can be alerted on actions as they happen. The events that are collected comply with the Cloud Auditing Data Federation (CADF) standard. For more information, see [Getting started with {{site.data.keyword.at_full_notm}}](/docs/Activity-Tracker-with-LogDNA?topic=Activity-Tracker-with-LogDNA-getting-started).






