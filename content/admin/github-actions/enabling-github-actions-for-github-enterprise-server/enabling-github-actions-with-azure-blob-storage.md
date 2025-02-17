---
title: Enabling GitHub Actions with Azure Blob storage
intro: 'You can enable {% data variables.product.prodname_actions %} on {% data variables.product.prodname_ghe_server %} and use Azure Blob storage to store artifacts generated by workflow runs.'
permissions: 'Site administrators can enable {% data variables.product.prodname_actions %} and configure enterprise settings.'
versions:
  ghes: '>=3.0'
topics:
  - Enterprise
redirect_from:
  - /admin/github-actions/enabling-github-actions-with-azure-blob-storage
---
## Prerequisites

Before enabling {% data variables.product.prodname_actions %}, make sure you have completed the following steps:

* Create your Azure storage account for storing workflow artifacts. {% data variables.product.prodname_actions %} stores its data as block blobs, and two storage account types are supported:
  * A **general-purpose** storage account (also known as `general-purpose v1` or `general-purpose v2`) using the **standard** performance tier.

    {% warning %}

    **Warning:** Using the **premium** performance tier with a general-purpose storage account is not supported. The **standard** performance tier must be selected when creating the storage account, and it cannot be changed later.

    {% endwarning %}
  * A **BlockBlobStorage** storage account, which uses the **premium** performance tier.

  For more information on Azure storage account types and performance tiers, see the [Azure documentation](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-overview?toc=/azure/storage/blobs/toc.json#types-of-storage-accounts).
{% data reusables.actions.enterprise-common-prereqs %}

## Enabling {% data variables.product.prodname_actions %} with Azure Blob storage

{% data reusables.enterprise_site_admin_settings.access-settings %}
{% data reusables.enterprise_site_admin_settings.management-console %}
{% data reusables.enterprise_management_console.actions %}
{% data reusables.actions.enterprise-enable-checkbox %}
1. Under "Artifact & Log Storage", select **Azure Blob Storage**, and enter your Azure storage account's connection string. For more information on getting the connection string for your storage account, see the [Azure documentation](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage?tabs=azure-portal#view-account-access-keys).
  ![Radio button for selecting Azure Blob Storage and the Connection string field](/assets/images/enterprise/management-console/actions-azure-storage.png)
{% data reusables.enterprise_management_console.save-settings %}

{% data reusables.actions.enterprise-postinstall-nextsteps %}
