# Set up the Workshop Environment

<!---
comments syntax
--->

## Introduction

This workshop focuses on teaching you how to setup your Autonomous AI Database and use Select AI Ask Oracle Chatbot application to query your data using natural language. The **Ask Oracle** APEX application, powered by Select AI and running on Autonomous AI Database, offers a conversational interface for interacting with your data. 

This short demo showcases how the app leverages Natural Language to SQL (NL2SQL), Retrieval-Augmented Generation (RAG), and AI agents to transform natural language queries into actionable insights.

[Ask Oracle Chatbot Demo](youtube:p595Io2cxyw:medium)





Estimated Time: 5 minutes.

### Objectives

In this lab, you will:

* Provision your Autonomous AI Database instance
* Install the Select AI Ask Oracle Chatbot application


## Task 1: Provision an Oracle Autonomous AI Database

[](include:adb-provision-body.md)

## Task 2: TEST

[](include:oml-prov-an-adb.md)

## Task 2: Grant Privileges

1. Login to **Database Actions** -> **SQL** as an `ADMIN`.
2. Grant the following to the schema user:

    ```
    <copy>
    GRANT EXECUTE on DBMS_CLOUD_AI to <USER>;
    GRANT EXECUTE on DBMS_CLOUD_AI_AGENT to <USER>;
    GRANT EXECUTE on DBMS_CLOUD_PIPELINE to <USER>;
    GRANT EXECUTE on DBMS_VECTOR to <USER>;
    GRANT CREATE ANY INDEX to <USER>;
    </copy>
    ```
> Replace `<USER>` with the schema user name.

## Task 2: Install Ask Oracle Chatbot Application
Perform the following steps to install the Ask Oracle Chatbot app. The application is available on GitHub.

1. Download the `ADB-AskOracle-Chatbot-yyyy-mm-dd.sql` file from the [GitHub repository](https://github.com/oracle-devrel/oracle-autonomous-database-samples/tree/main/apex/Ask-Oracle) and store it in your local directory. 

2. From your Autonomous AI Database console, navigate to **Tool configuration** and copy the APEX URL.

3. Paste the URL in your web browser and **Sign In** with the workspace associated with the created schema.
    >If you haven't created your workspace, click **Administration Services** on the APEX workspace login screen and create one.

4. In APEX, go to **App Builder** → **Import**.

5. Click the **Drag and Drop** selection and navigate to the `ADB-AskOracle-Chatbot-yyyy-mm-dd.sql` file that you stored in your local directory and click **Open**.

6. Keep the defaults and click **Next**.

7. Next screen, click **Install Application**. This may take a while. Once the application is installed, click **Next**.

8. Review the supporting objects and click **Install Supporting Objects**.

9. Next screen shows a confirmation screen with the supporting objects installed, click **Run Application**.

10. You'll be prompted with a login screen. Enter the **Ask Oracle** username and password. You are ready with a prompt screen.

Here is a video that walks you through the **Ask Oracle** chatbot app installation:
[Ask Oracle App Installation](youtube:kjeQ2AC3TFo:medium)



You may now proceed to the next lab.

## Learn More

* [Using Oracle Autonomous AI Database Serverless](https://docs.oracle.com/en/cloud/paas/autonomous-database/adbsa/index.html)
* [Select AI Examples](https://docs.oracle.com/en/cloud/paas/autonomous-database/serverless/adbsb/select-ai-examples.html#GUID-8BEF8CA8-D98D-41FB-A819-6C2F862099DC)

## Acknowledgements

* **Author:** Sarika Surampudi, Principal User Assistance Developer
* **Contributor:** Mark Hornick, Product Manager
<!--* **Last Updated By/Date:** Sarika Surampudi, August 2025
-->


Copyright (c) 2025 Oracle Corporation.

Permission is granted to copy, distribute and/or modify this document
under the terms of the GNU Free Documentation License, Version 1.3
or any later version published by the Free Software Foundation;
with no Invariant Sections, no Front-Cover Texts, and no Back-Cover Texts.
A copy of the license is included in the section entitled [GNU Free Documentation License](https://oracle-livelabs.github.io/adb/shared/adb-15-minutes/introduction/files/gnu-free-documentation-license.txt)
