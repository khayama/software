---
copyright:
  years: 1994, 2017
lastupdated: "2017-08-23"
---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}



# RedHat Update Instructions

IBM provides OS and software update services for RedHat environments free of charge.

All update services at IBM share the following features:
* Update traffic is routed from your server (over your private VLAN) to the private service network
* Update traffic is part of your unlimited private network bandwidth and does not reduce public bandwidth allotments.
* Updates speeds are faster than updating from vendors directly (upgraded ports speeds available on demand)
* Updates are readily available during worldwide heavy critical update days.
* In emergency situations, public ports can be shut down while still allowing updates to occur over the private network
* Servers are pre-configured to update automatically at deployment with manual updates available on demand.

IBM update servers are in the private service network with the following location identifiers:

|Datacenter|Service Host Address|
|---|---|
|Amsterdam|rhnproxyams0101.service.softlayer.com|
|Dallas|rhnproxy101.service.softlayer.com|
|Houston|rhnproxy421.service.softlayer.com|
|San Jose|rhnproxy501.service.softlayer.com|
|Seattle|rhnproxy201.service.softlayer.com|
|Singapore|rhnproxysng0101.service.softlayer.com|
|Washington D.C.|rhnproxy301.service.softlayer.com|

Always test kernel or service pack upgrades before installation on production server environments. You can find technical information that is related to specific hardware, OS, and applications deployed in the FAQ or drivers section inside the customer Web Portal. IBM tests kernel and service pack upgrades and post related information (including drivers) to help the upgrade process.

## RHN Subscription

For RedHat operating systems, IBM provides RedHat Network Satellite servers to install critical and non-critical security updates.

The RedHat Network at SoftLayer includes RHN Satellite and Proxy servers. When your RedHat server is provisioned, it is automatically registered to the IBM RHN Satellite server by using the appropriate proxy server. This registration allows you to use **up2date** commands locally on your servers and pull updates across the private service network.

To ensure enterprise quality of service and facilitate proper change management techniques, RedHat OS servers are configured by default to skip kernel updates. To ensure system stability, perform kernel upgrades manually after you complete regression testing. IBM uses leading-edge hardware technologies that require stable kernel editions for proper performance.
