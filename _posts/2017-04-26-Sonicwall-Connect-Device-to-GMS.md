---
layout: default
title: How-To connect SonicWALL device to Global Management System (GMS)
author: robss_it
categories: SonicWALL, GMS, integration
tags: SonicWALL, GMS, integration
---

The steps to connect a SonicWALL device to a GMS system are detailed below.

After logging into the device management interface complete the following steps.

1. Select System -> Administration
2. Select "Enable management using GMS" checkbox
3. Select "Configure" button

In the "Configure GMS settings" windows complete the required fields.

4. Enter the Internal IP of the GMS host in the "GMS Host Name or IP Address" field
5. Select "GMS behind NAT device" checkbox and enter the Public IP of the GMS host
6. Optional: Select "Send Syslog Messages to a distributed GMS Server", enter the Internal IP of the GMS host in the "GMS Reporting Server IP Address" field and the port in "GMS Reporting Server Port"


These steps are depicted in the following screenshot.

![4-26-2017-GMS-How-To-Connect-Device.jpg]({{site.url/assets/images/4-26-2017-GMS-How-To-Connect-Device.jpg}})