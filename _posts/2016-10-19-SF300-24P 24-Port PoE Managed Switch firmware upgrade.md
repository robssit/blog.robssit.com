---
layout: default
title: SF300-24P 24-Port 10/100 PoE Managed Switch firmware upgrade
author: robss_it
categories: switchvox, networking, switch, cisco, firmware, upgrade
tags: switchvox, networking, switch, cisco, firmware, upgrade
---

In working through an issue with a Switchvox phone system dropping calls, I found that a particular switch seemed to be the cause of the issue.

The switch in question is a Cisco [SF300-24P] [1].

An intital wireshark capture showed the following 'Frame Check Sequence' error.

![cisco-spf-300-fcs-error.jpg]({{ site.url }}/assets/images/cisco-spf-300-fcs-error.jpg)


The switch initially had the following bootrom and firmware versions installed.


|   item   | Version  |
| :------: | :------: |
| bootrom  | 1.0.0.4  |
| firmware | 1.0.0.27 |


The [release notes] [2] indicate a change in the flash filesystem which required an intermediate upgrade.
The updated firmwares were downloaded from [SF300-24P Downloads] [3] and upgraded in the following order.


|  Task   |   Item   | Version  |
| :-----: | :------: | :------: |
| upgrade | firmware | 1.3.5.58 |
| upgrade | firmware | 1.3.7.18 |
| upgrade | bootrom  |  13506   |
| upgrade | firmware | 1.4.5.02 |

After a series of reboots and configuration backups a second wireshark capture showed no further errors.

![cisco-spf-300-fcs-no-error.jpg]({{ site.url }}/assets/images/cisco-spf-300-fcs-no-error.jpg)



[1]: http://www.cisco.com/c/en/us/support/switches/sf300-24p-24-port-10-100-poe-managed-switch-gigabit-uplinks/model.html "SF300-24P"
[2]: http://www.cisco.com/c/dam/en/us/td/docs/switches/lan/csbms/sf30x_sg30x/release_notes/R_1_4_5_02_RN.pdf "release notes"
[3]: http://www.cisco.com/c/en/us/support/switches/sf300-24p-24-port-10-100-poe-managed-switch-gigabit-uplinks/model.html#~tab-downloads "SF300-24P Downloads"