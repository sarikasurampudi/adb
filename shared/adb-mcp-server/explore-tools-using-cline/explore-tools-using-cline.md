# Explore Tools in MCP Server Using Cline Extension

## Introduction

In the previous lab, you configured Visual Studio Code with the Cline extension to connect to the Autonomous AI Database MCP Server.

In this lab, you use Cline to process natural language prompts and call the database tools created in *Lab 3*.

You will review tool call requests, approve tool usage, and analyze structured results returned from the database.

This lab demonstrates how Cline processes requests and loads database results using the MCP Server.

Estimated Time:x

### Objectives

In this lab, you will:

* Issue natural language prompts in Cline
* Review tool call requests
* Approve tool usage
* Observe how Cline processes multi-step requests
* Analyze formatted database results

### Prerequisites

- This lab requires completion of Lab 1 through Lab 3 and Lab 6 in the **Contents** menu on the left.


## Task 1: Discover Available Schemas
In this task, you ask Cline to retrieve the list of schemas available in your Autonomous AI Database. Cline processes your natural language prompt, selects the appropriate tool, and calls the database to load schema information.
1. In the **Type your task here...** chat field, type the following prompt and press **Enter** :

    _What schemas are available in the database?_

![Enter prompt to list schemas](./images/cline-list-schemas.png =70%x*)

2. Cline selects the LIST_SCHEMAS tool. Review the tool call details.
3. Click **Approve**.
    ![Approve the list schemas tool](./images/cline-list-schemas-approve.png =70%x*)
4. A formatted list of schemas is displayed.
![List schemas result](./images/cline-list-schemas-result.png =70%x*)


## Task 2: List Objects in a Schema

In this task, you ask Cline to retrieve database objects within a specific schema. Cline processes the prompt and calls the appropriate tool to load object information.
1. Type the following prompt in the chat field and press **Enter**:

    _What objects exist in the sales\_user schema?_
    ![Enter prompt to list objects](./images/cline-list-objects.png =70%x*)
2. Cline selects LIST_OBJECTS.
3. Click **Approve**.
    ![Approve the list objects tool](./images/cline-list-objects-approve.png =70%x*)
4. Object names and types are returned that match the `SALES_USER` schema.
    ![List objects result](./images/cline-list-objects-result.png =70%x*)


## Task 3: Retrieve Object Metadata
In this task, you request detailed metadata for a specific table. Cline processes the request and calls the metadata tool to load structural information.

1. Issue a new prompt and press **Enter**:

    _Show the metadata details of the customer table_
    ![Enter prompt to list objects](./images/cline-get-object-details.png =70%x*)
2. Cline selects GET\_OBJECT\_DETAILS.
3. Click **Approve**.
    ![Approve the list objects tool](./images/cline-get-object-details-approve.png =70%x*)
4. Structured metadata is displayed.
    ![GET\_OBJECT\_DETAILS result](./images/cline-get-object-details-result.png =70%x*)


## Task 4: Process a Business Query
In this task, you ask Cline to retrieve business data using a natural language query. Cline processes the request, selects the SQL tool, and calls the database to load the required data.
1. Issue a new prompt and press **Enter**:

    _Show top 3 customers by revenue in each region_

    ![Enter prompt to for top 3 customers](./images/cline-top3-customers-prompt.png =70%x*)
2. Cline selects LIST\_OBJECTS first. This step may vary and the LLM may present other options.
    ![Approve `LIST_OBJECTS`](./images/cline-top3-customers-list-objects.png =70%x*)

3. Click **Approve**.
4. Now, Cline selects EXECUTE\_SQL.
    ![Approve `EXECUTE_SQL`](./images/cline-top3-customers-execute-sql.png =70%x*)
5. Click **Approve**.
6. Then, Cline wants to use GET\_OBJECT\_DETAILS.
    ![Approve `GET_OBJECT_DETAILS`](./images/cline-top3-customers-get-object-details.png =70%x*)
7. Click **Approve**.
8. Cline again uses GET_OBJECT_DETAILS for ORDER_ITEMS.
    ![Approve `GET_OBJECT_DETAILS`](./images/cline-order-items-approve.png =70%x*)
9. Click **Approve**.
10. Cline finally uses EXECUTE_SQL.
    ![Approve `EXECUTE_SQL`](./images/cline-execute-sql-order-items-approve.png =70%x*)
11. Click **Approve**.
12. Cline displays a summarized and structured result and completes the task.
    ![Approve `EXECUTE_SQL`](./images/cline-execute-sql2-result.png =70%x*)


**This concludes your workshop**

## Learn More

* [Select AI Agent](https://docs.oracle.com/en/cloud/paas/autonomous-database/serverless/adbsb/select-ai-agent1.html)
* [Select AI Agent Package](https://docs.oracle.com/en/cloud/paas/autonomous-database/serverless/adbsb/dbms-cloud-ai-agent-package.html)
* [OML Notebooks](https://docs.oracle.com/en/database/oracle/machine-learning/oml-notebooks/index.html)
* [Using Oracle Autonomous AI Database Serverless](https://docs.oracle.com/en/cloud/paas/autonomous-database/adbsa/index.html)


## Acknowledgements

* **Author:** Sarika Surampudi, Principal User Assistance Developer
* **Contributor:** Mark Hornick, Product Manager; Laura Zhao, Member of Technical Staff
<!--* **Last Updated By/Date:** Sarika Surampudi, August 2025
-->


Copyright (c) 2026 Oracle Corporation.

Permission is granted to copy, distribute and/or modify this document
under the terms of the GNU Free Documentation License, Version 1.3
or any later version published by the Free Software Foundation;
with no Invariant Sections, no Front-Cover Texts, and no Back-Cover Texts.
A copy of the license is included in the section entitled [GNU Free Documentation License](https://oracle-livelabs.github.io/adb/shared/adb-15-minutes/introduction/files/gnu-free-documentation-license.txt)
