splunk-app-pvs
==============

Tenable Network Security PVS App for Splunk

Introduction:
=============

The Tenable Passive Vulnerability Scanner™ (PVS™) monitors network traffic 
at the packet layer to determine topology and identify services, security 
vulnerabilities, suspicious network relationships, and compliance 
violations. The PVS™ app for Splunk provides overview reports and searching 
of the realtime event data generated by PVS. 


Requirements:
=============

* Tenable Passive Vulnerability Scanner, version 4.x or higher. To obtain a PVS
evalutation see: http://www.tenable.com/products/passive-vulnerability-scanner/evaluate
* Splunk 6.x or higher.

A separate index will be created and used for PVS data. This is done for search 
time performance, and it can also be used to control access to the data.


Configuration:
==============

From the PVS UI, go to “Configuration”. 

Select Syslog in the "Setting Type" dropdown.

Enter the IP and UDP port of the Splunk server in the "Realtime Syslog Server 
List".

Note: Must be entered as IP:PORT (e.g. 10.1.1.10:514).


Configuring props.conf
----------------------

The Tenable PVS Splunk App is designed to communicate natively using a UDP 
port on the Splunk Indexer with a sourcetype of [syslog]. This can be a shared 
input using the sourcetype of [syslog], or if another port is to be used then a 
new input can be added with the sourcetype of [pvs]. Refer to `props.conf` 
located in the `$SPLUNK_HOME/etc/apps/pvs/default/props.conf` file which may need to be 
altered to reflect the new configurations. More information on configuring the 
`props.conf` file can be found at 
http://docs.splunk.com/Documentation/Splunk/latest/Admin/Propsconf 


Author Information:
===================

Author: Tenable Network Security, Inc.

If you need assistance see the PVS Discussion Forum located at: 
https://discussions.nessus.org/community/pvs


Disclaimer:
===========

PVS is the property of Tenable Network Security, Inc.

