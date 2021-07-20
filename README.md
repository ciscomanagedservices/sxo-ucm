## SecureX Orchestrator Atomic Actions for Cisco Unified Communications Manager (CUCM)

Please update the namespaces and the SOAPAction Header based on the version & schema you're working with. At present, the atomic actions are setup & tested to work with UCM v12.5.

### In this repository, you'll find the following atomics:

#### 1. [Execute SQL Query](/UCM-ExecuteSQLQuery__definition_workflow_01ORXH3VZ8VGW1VbFMDxTC1BgOhecPbx7pB/)

> **Purpose:** Run an SQL Query via UCM's AXL API

Steps to use:
1. Setup your UCM Target & Account Key as AXL Credential
2. Provide SQL Query to run as input
3. If the request is successful, the output of this atomic is an XML string w/ the rows as seen in the SQL response
4. If the request is not successful, the output contains the error message

TIP: If you're doing a SELECT query, use 'Read Table from XML' w/ the XML output in your workflow to have a table object you can iterate over.

---

#### 2. [Add Phone](/UCM-AddPhone__definition_workflow_01P254MUSZTTR78gPMCWX2uz8NOLp5Po7o7/)

> **Purpose:** Create a new phone via UCM's AXL API

Steps to use:
1. Setup your UCM Target & Account Key as AXL Credential
2. Provide a JSON input with one or more of the supported fields for the addPhone AXL method (refer to README on Git repo for steps on how to generate this)
3. If the request is successful, the output of this atomic is the UID response string returned from UCM for the added phone
4. If the request is not successful, the output contains the error message

---

#### 3. [Get Phone](/UCM-GetPhone__definition_workflow_01PZZCV7XGGPX1kvQJbYuWXYT9oLo3vtc2a)

> **Purpose:** Retrieve details of a phone via UCM's AXL API

Steps to use:
1. Setup your UCM Target & Account Key as AXL Credential
2. Provide the Name or UUID of the phone to retrieve details. You must provide one of the two.
3. You can also input a comma-separated list of what fields you'd like to have returned or leave the 'Fields to Return' input blank to return all fields
4. If the request is successful, the output of this atomic is the XML response string returned from UCM for the searched
5. If the request is not successful, the output contains the error message

---

#### 4. [Run Terminal Command](/UCM-RunTerminalCommand__definition_workflow_01Q04YJXJPLUU7mb55fQorftOQGv4CRVtKw)

> **Purpose:** Run a Terminal (CLI) Command on UCM/UCOS

Steps to use:
1. Setup a Terminal Endpoint for your UC Application & Account Key as OS/Platform credential. Under 'Terminal Interaction Patterns (regex)', set the prompt to `admin:`.
2. Provide a list of commands as input (one per line). It is recommended to send more than one command at once to avoid having to recreate separate SSH sessions.
3. The output of this atomic action is a table with CLI Commands & their Outputs

---

Contributors:

1. Aman Sardana (amasarda@cisco.com)
2. Saurabh Khaneja (sakhanej@cisco.com)

Cisco CX Managed Services - Operate &amp; CX Professional Services, May 2021
