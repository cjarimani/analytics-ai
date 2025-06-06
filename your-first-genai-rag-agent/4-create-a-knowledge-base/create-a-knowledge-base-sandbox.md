# Create a knowledge base

## Introduction

In this lab we are going to create a knowledge base which will consist of the text files we've uploaded to the storage bucket.
A Knowledge Base maintains information about the Data Source (where the data comes from, for example, text files in storage bucket) as well as metadata for accessing that data and in certain cases, it would also manage indexing and vector storage for the data.
Creating a Knowledge Base lets the OCI Generative AI Agents service know where our data is stored and what format it is stored in. Using this information, the service will be able to ingest the data, understand it and index it for fast retrieval later.
A single knowledge base can be used for multiple Agents.

Estimated Time: 15 minutes

### Objectives

In this lab, you will:

* Create a knowledge base.
* Monitor the ingestion job.

### Prerequisites

This lab assumes you have:

* An Oracle Cloud account
* All previous labs successfully completed

## Task 1: Create a knowledge base

1. From the OCI Generative AI Agents service overview page, click the **Knowledge Bases** link on the left.

1. Make sure that the compartment created for you as part of the Sandbox environment is selected in the **Compartment** list under the **List scope** section on the left. See [Get Started](?lab=cloud-login-livelabs2) for help with locating the compartment name. Please note that you may have to expand the **root** and **LiveLabs** compartments in order to locate the right compartment.

1. Click the **Create knowledge base** button at the top of the **Knowledge bases** table.

  ![Screenshot showing how to navigate to the knowledge base sections within the agents service console](./images/knowledge-base-navigation.png)

1. Provide a name for the Knowledge base (for example: oci-generative-ai-agents-cw24-hol-kb)

1. Make sure that the compartment created for you as part of the Sandbox environment is selected in the **Compartment** list. See [Get Started](?lab=cloud-login-livelabs2) for help with locating the compartment name. Please note that you may have to expand the **root** and **LiveLabs** compartments in order to locate the right compartment.

1. Make sure that the **Object storage** option is selected in the **Select data store** list.

1. Click the **Create data source** button at the top of the **Data sources** table.

1. In the **Create data source** pane, provide a name for the data source (for example: oci-generative-ai-agents-cw24-hol-ds)

1. In the **Data bucket** section, make sure that the compartment created for you as part of the Sandbox environment is selected. If not, click the **Change compartment** link and select right compartment. See [Get Started](?lab=cloud-login-livelabs2) for help with locating the compartment name. Please note that you may have to expand the **root** and **LiveLabs** compartments in order to locate the right compartment.

1. Select the storage bucket into which you've uploaded the dataset text files in the previous lab.

1. Select the **Select all in bucket** option from the **Object prefixes** list.

1. Click the **Create** button at the bottom of the pane.

  ![Screenshot showing the configuration for the data source](./images/create-data-source.png)

1. Make sure that the **Automatically start ingestion job for above data sources** option is checked.

1. Click the **Create** button at the bottom of the page.

  ![Screenshot showing how to complete the knowledge base configuration](./images/create-knowledge-base.png)

If everything went to plan, your Knowledge Base will be created. This can take a few minutes.

Please wait until the **Lifecycle state** shows the **Active** state before moving on to the next lab.

  ![Screenshot showing the created knowledge base](./images/knowledge-base-created.png)

  ![Screenshot showing the active knowledge base](./images/knowledge-base-active.png)

## Task 2: Monitor the ingestion job

When a Knowledge Base is created, an Ingestion Job is automatically created in order to process the information contained in the Data Source.
This job might take a while to complete and the Knowledge Base will not be set to Active until it is done.
Here are the steps to monitor the Ingestion Job's progress.

1. From the OCI Generative AI Agents service overview page, click the **Knowledge Bases** link on the left.

1. Make sure that the compartment created for you as part of the Sandbox environment is selected in the **Compartment** list under the **List scope** section on the left. See [Get Started](?lab=cloud-login-livelabs2) for help with locating the compartment name. Please note that you may have to expand the **root** and **LiveLabs** compartments in order to locate the right compartment.

1. Click the Knowledge Base we've just created in the previous task in the **Knowledge bases** table.

  ![Screenshot showing how to navigate to the newly created knowledge base](./images/view-knowledge-base-navigation.png)

1. In the Knowledge Base details page, click the Data Source we've created in the previous task in the **Data sources** table.

  ![Screenshot showing how to navigate to the data source within the knowledge base](./images/data-source-navigation.png)

1. In the Data Source details page, click the Ingestion Job which was automatically created (should only be one) in the **Ingestion jobs** table.

  ![Screenshot showing how to navigate to the ingestion job initiated for the data source](./images/ingestion-job-navigation.png)

1. In the Ingestion job details page you'll be able to see the job progress under the **Work requests** table by observing the **State** and **Percent complete** columns. Initially the it will look like this:

  ![Screenshot showing the ingestion job details highlighting that it is in progress at the moment](./images/ingestion-job-details.png)

  When the Ingestion Job is complete, it should look this:

  ![Screenshot showing additional details for the ingestion job like the number of files ingested or failed](./images/ingestion-job-completed.png)

  As you can see, details page displays information such as: **Number of ingested files**, **Number of failed files**, **Job duration** and more. When the job is complete, the **Percent complete** column should show 100% and the **State** column should indicate **Succeeded**. At this point you can continue to the next lab.

## Acknowledgements

* **Author** - Lyudmil Pelov, Senior Principal Product Manager, Yanir Shahak, Senior Principal Software Engineer
