---
title: Setup API provisioning
description: Step-by-step instructions for setting up one-time or automatic provisioning of Microsoft Academic Knowledge Exploration Service APIs to an Azure blob storage account
ms.topic: get-started-article
ms.date: 03/18/2018
---
# Get started with Microsoft Academic Knowledge Exploration Service

> [!IMPORTANT]
> We will be publishing a new version of MAKES in early 2020.  This version will be a turn-key solution to host MAKES in your Azure subscription.  For users of [Project Academic Knowledge](https://www.microsoft.com/research/project/academic-knowledge/), this MAKES version will mirror the schema and API methods supported by that project, enabling users to host their own un-throttled version of the API's.

Details step-by-step instructions for setting up one-time or automatic provisioning of Microsoft Academic Knowledge Exploration Service APIs to an Azure blob storage account.

## Open Data License: [ODC-BY](https://opendatacommons.org/licenses/by/1.0/)

When using Microsoft Academic data (MAG, MAKES, etc.) in a product or service, or including data in a redistribution, please acknowledge Microsoft Academic using the URI https://aka.ms/msracad. For publications and reports, please cite the following article:

> [!NOTE]
> Arnab Sinha, Zhihong Shen, Yang Song, Hao Ma, Darrin Eide, Bo-June (Paul) Hsu, and Kuansan Wang. 2015. An Overview of Microsoft Academic Service (MA) and Applications. In Proceedings of the 24th International Conference on World Wide Web (WWW '15 Companion). ACM, New York, NY, USA, 243-246. DOI=http://dx.doi.org/10.1145/2740908.2742839

## Pre-requisites

- [Azure account + subscription](https://azure.microsoft.com/get-started)
- [Azure Storage account](https://docs.microsoft.com/azure/storage/)

## Setup storage account to receive MAKES API builds

### [Create an Azure Subscription](https://azure.microsoft.com/get-started)

Please create a new Azure subscription for the distribution previews. If your organization already using Azure, this could be a separate subscription under the same tenant id. If you start from scratch, for example “create Azure free account”, the subscription will be created under a new tenant id.

### [Create an Azure Storage Account](https://docs.microsoft.com/azure/storage/common/storage-quickstart-create-account?tabs=portal)

1. Home > Create a resource > Storage > Storage account

    ![Create new azure storage account](media/create-azure-storage-account.png "Create new azure storage account")

2. Specify “makesas<org_name>” for the account name, “classic” for deployment model, “LRS” for replication, “standard” for performance and “makes” for the resource group

    ![Configure azure storage account details](media/create-azure-storage-account-configure.png "Configure azure storage account details")

    > [!IMPORTANT]
    > You don’t need to use your organization name after the “makesas”, however the account name must be unique among all Azure Storage Accounts

    > [!NOTE]
    > Select whatever region is most appropriate for your existing Azure resources

3. Once notified that the storage account has been created, click “go to resource”

    ![Go to new azure storage account](media/create-azure-storage-account-go-to.png "Go to new azure storage account")

4. Go to “access keys” and take note of the “storage account name” and the “primary key”

    ![Copy new azure storage account details](media/create-azure-storage-account-copy-details.png "Copy new azure storage account details")

5. To sign up for the MAKES API distribution preview, send the following details to <a href="mailto:academicapi@microsoft.com?subject=Access request to Microsoft Academic Knowledge Exploration Service (MAKES) distribution preview">academicapi@microsoft.com</a> with the subject "Access request to Microsoft Academic Knowledge Exploration Service (MAKES) distribution preview":

    - Are you affiliated with a company or university?
        - If company, please provide the company’s name, your department/group and your role
        - If university, please provide the university’s name, department, group/advisor, and your role (undergraduate student, grad student, professor, etc.)
    - Brief description of the project you will be using MAKES for
    - Name of your Microsoft sales representative, if you have one
    - Azure storage account name
    - Azure storage account primary access key
    - Which MAKES APIs you want to receive (semantic interpretation API, entity API, or both)

    > [!NOTE]
    > MAKES is currently in a free preview period, so there are no charges associated with the provisioning or use of data/service itself. However Azure requires you to cover all costs associated with standard resource creation, usage, etc. For cost estimates associated with MAKES please see the [Pricing](resources-pricing.md) page. <br/><br/>Most research institutions have an "Enterprise Account" with Microsoft including Azure subscription. The pricing for Enterprise Accounts differ from the individual account shown in Azure's price calculator. <br/><br/>If you have an Enterprise Account, please check with your individual institution's Information Technology/Computer Center resource on the process of setting up Azure to get MAKES. You might need to obtain a "Master Agreement #" and involve MLSP (Microsoft Licensed Solution Provider) for help.

## API release process

MAKES API builds are deployed approximately once a week to all Azure storage accounts that are signed up for the distribution preview.

Each API build has a unique name reflecting the date it was created, and is placed in the following location:

- makes
  - YYYY-MM-DD (release date)
    - entity-engine
    - semantic-interpretation-engine

Example:

![API release location in blob storage](media/api-release-location.png "API release location in blob storage")
