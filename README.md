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

Contributors:

1. Aman Sardana (amasarda@cisco.com)
2. Saurabh Khaneja (sakhanej@cisco.com)

Cisco CX Managed Services - Operate &amp; CX Professional Services, May 2021
