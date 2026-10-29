
<h1>Splunk SIEM Fundamentals & Environment Setup</h1>

<h2>Description</h2>

This phase documents the setup of a Splunk SIEM environment and introduces the fundamental concepts used to collect, search, and analyze security data. The goal of this phase is to establish a working Splunk environment while developing familiarity with the platform before performing security-focused investigations in later phases.

<br />In this phase, the following topics will be covered:
- <b>Ubuntu Server installation and configuration</b>
- <b>VirtualBox networking</b>
- <b>Splunk installation and configuration</b>
- <b>Splunk interface navigation</b>
- <b>Data ingestion</b>
- <b>Indexes</b>
- <b>Sourcetypes</b>
- <b>Events</b>
- <b>Fields</b>
- <b>Basic SPL searches</b>
- <b>Search filtering</b>
- <b>Common SPL commands</b>
- <b>Splunk data pipeline fundamentals</b>

This phase establishes the foundational Splunk knowledge and environment required for the security analysis, detection, and automation performed throughout the project.
<br />

<h2>Languages and Utilities Used</h2>

- <b>Splunk Enterprise</b>
- <b>Splunk Processing Language (SPL)</b>
- <b>Ubuntu Server 24.04.5 LTS</b>
- <b>Linux Command Line</b>
- <b>OpenSSH</b>
- <b>Web Browser</b>
- <b>Oracle VirtualBox</b>
- <b>Additional Splunk applications introduced throughout the project</b>

<h2>Environments Used</h2>

- <b>Host Operating System: Windows 11</b>
- <b>Virtualization Platform: Oracle VirtualBox</b>
- <b>Splunk SIEM Server: Ubuntu Server 24.04.5 LTS</b>
- <b>Active Directory Lab: Windows Server 2022 and Windows 11</b>

<h2>Program walk-through:</h2>

<p align="center">
<b>Step 1 – Install and Configure Ubuntu Server</b><br/><br/>
Create a dedicated Splunk-SIEM virtual machine in Oracle VirtualBox using Ubuntu Server 24.04.5 LTS. Allocate 8 GB of RAM, 4 CPU cores, and a 100 GB virtual disk. Complete the Ubuntu installation, configure the administrator account, and install available system updates:<br/>
<a href="https://raw.githubusercontent.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-1/main/Step1.png"><img src="https://github.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-1/blob/main/Step1.png?raw=true" height="80%" width="80%" alt="Project Steps"/></a>
</p>

<p align="center">
<b>Step 2 – Configure VirtualBox Networking</b><br/><br/>
Configure the Splunk virtual machine with a NAT adapter for internet connectivity and a Host-Only adapter for communication with the Windows host computer. Assign the Ubuntu server a static IP address of 192.168.56.20 and verify connectivity to the Windows host at 192.168.56.1. Confirm internet access by successfully pinging google.com. Communication with the other Active Directory lab virtual machines will be configured and tested in later phases:<br/>
<a href="https://raw.githubusercontent.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-1/main/Step2.png"><img src="https://github.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-1/blob/main/Step2.png?raw=true" height="80%" width="80%" alt="Project Steps"/></a>
</p>

<p align="center">
<b>Step 3 – Install Splunk Enterprise</b><br/><br/>
Download and install Splunk Enterprise on the Ubuntu Server virtual machine. Configure the initial administrator account and prepare the Splunk service for operation:<br/>
<a href="https://raw.githubusercontent.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-1/main/Step3.png"><img src="https://github.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-1/blob/main/Step3.png?raw=true" height="80%" width="80%" alt="Project Steps"/></a>
</p>

<p align="center">
<b>Step 4 – Access the Splunk Web Interface</b><br/><br/>
Start the Splunk service and access the Splunk Web interface through a browser. Sign in using the administrator credentials and verify that the Splunk environment is operational:<br/>
<a href="https://raw.githubusercontent.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-1/main/Step4.png"><img src="https://github.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-1/blob/main/Step4.png?raw=true" height="80%" width="80%" alt="Project Steps"/></a>
</p>

<p align="center">
<b>Step 5 – Explore the Splunk Interface</b><br/><br/>
Navigate the Splunk Web interface and become familiar with the Search & Reporting application, Settings menu, data management options, and administrative features:<br/>
<a href="https://raw.githubusercontent.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-1/main/Step5.png"><img src="https://github.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-1/blob/main/Step5.png?raw=true" height="80%" width="80%" alt="Project Steps"/></a>
</p>

<p align="center">
<b>Step 6 – Ingest Sample Data into Splunk</b><br/><br/>
Import sample log data into Splunk using the Add Data interface. Review the available data ingestion methods and verify that events are successfully indexed and searchable:<br/>
<a href="https://raw.githubusercontent.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-1/main/Step6.png"><img src="https://github.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-1/blob/main/Step6.png?raw=true" height="80%" width="80%" alt="Project Steps"/></a>
</p>

<p align="center">
<b>Step 7 – Understand Indexes and Sourcetypes</b><br/><br/>
Explore how Splunk organizes incoming data using indexes and sourcetypes. Identify the index and sourcetype assigned to the ingested sample data and examine their roles in searching and categorizing events:<br/>
<a href="https://raw.githubusercontent.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-1/main/Step7.png"><img src="https://github.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-1/blob/main/Step7.png?raw=true" height="80%" width="80%" alt="Project Steps"/></a>
</p>

<p align="center">
<b>Step 8 – Examine Events and Fields</b><br/><br/>
Review individual log events within Splunk and identify extracted fields such as timestamps, hosts, sources, and sourcetypes. Explore how fields provide structured information that can be used during investigations:<br/>
<a href="https://raw.githubusercontent.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-1/main/Step8.png"><img src="https://github.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-1/blob/main/Step8.png?raw=true" height="80%" width="80%" alt="Project Steps"/></a>
</p>

<p align="center">
<b>Step 9 – Perform Basic SPL Searches</b><br/><br/>
Use Splunk Processing Language to search the ingested data. Practice selecting indexes, filtering by sourcetype, searching for keywords, and adjusting time ranges to locate relevant events:<br/>
<a href="https://raw.githubusercontent.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-1/main/Step9.png"><img src="https://github.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-1/blob/main/Step9.png?raw=true" height="80%" width="80%" alt="Project Steps"/></a>
</p>

<p align="center">
<b>Step 10 – Practice Common SPL Commands</b><br/><br/>
Explore commonly used SPL commands such as table, fields, sort, stats, and dedup. Use these commands to organize search results, calculate event counts, and summarize information within the ingested dataset:<br/>
<a href="https://raw.githubusercontent.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-1/main/Step10.png"><img src="https://github.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-1/blob/main/Step10.png?raw=true" height="80%" width="80%" alt="Project Steps"/></a>
</p>

<p align="center">
<b>Step 11 – Understand the Splunk Data Pipeline</b><br/><br/>
Review how Splunk processes incoming data through input, parsing, indexing, and search operations. Examine how raw log information becomes searchable events and how this process supports security monitoring:<br/>
<a href="https://raw.githubusercontent.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-1/main/Step11.png"><img src="https://github.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-1/blob/main/Step11.png?raw=true" height="80%" width="80%" alt="Project Steps"/></a>
</p>

<p align="center">
<b>Step 12 – Validate the Splunk SIEM Environment</b><br/><br/>
Verify that Splunk is running correctly, sample data is searchable, and basic SPL queries return expected results. Confirm that the environment is ready for more advanced data ingestion, parsing, and security analysis in Phase 2:<br/>
<a href="https://raw.githubusercontent.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-1/main/Step12.png"><img src="https://github.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-1/blob/main/Step12.png?raw=true" height="80%" width="80%" alt="Project Steps"/></a>
</p>
