# Connecting-an-Azure-VNet-VPN-to-a-local-FortiGate-with-APIPA-address-as-the-BGP-peer-IP


## Introduction

The main goal of this article is to help people who is going to configure VPN between Azure VPN Gateway and On-Prem Fortigate Firewall and enable the BGP routing protocol with APIPA address as the BGP peer IP.

**Note:** This guide assumes you have basic understanding of Azure VPN and Fortigate hands on experience.

## Topology

The following demonstrates the topology for this configuration:

![](.image/2021-01-30-14-28-57.png)

## Configure Virtual Network

In the Azure portal, go to Virtual Networks, select the Resource group, desired Name and Region, configure the IP addres space and Subnets for Virtual Machine and Virtual Network Gateway Subnet. Here is the example of result.
![](.image/2021-01-30-14-52-19.png)

If you are not familar with the Virtual Network creation, see how to create a Virtual Network using the Azure Portal: [Link](https://docs.microsoft.com/en-us/azure/virtual-network/quick-create-portal)