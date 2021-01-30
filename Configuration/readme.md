# Connecting-an-Azure-VNet-VPN-to-a-local-FortiGate-with-APIPA-address-as-the-BGP-peer-IP


## Introduction

The main goal of this article is to help people who is going to configure VPN between Azure VPN Gateway and On-Prem Fortigate Firewall and enable the BGP routing protocol with APIPA address as the BGP peer IP.

>**Note:** This guide assumes you have basic understanding of Azure VPN and Fortigate hands on experience.

## Topology

The following demonstrates the topology for this configuration:

![](.image/2021-01-30-14-28-57.png)

## Configure Virtual Network

In the Azure portal, go to Virtual Networks, select the Resource group, desired Name and Region, configure the IP addres space and Subnets for Virtual Machine and Virtual Network Gateway Subnet. Here is the example of result.
![](.image/2021-01-30-14-52-19.png)

If you are not familar with the Virtual Network creation, see how to create a Virtual Network using the Azure Portal: [Link](https://docs.microsoft.com/en-us/azure/virtual-network/quick-create-portal)

## Configure Azure Virtual Machine

We create a VM to demostrate as a VPN endpoint in Azure.
  - Create a VM in the desired Subnet, it would be "Subnet001" in my example. Check [Here](https://docs.microsoft.com/en-us/azure/virtual-network/quick-create-portal) if you are not familar with the Azure VM creation.
  - Check VM NSG to make sure the data traffic is not being blocked.

## Configure Azure VPN Gateway/Virtual Network Gateway

A VPN gateway is a specific type of virtual network gateway that is used to send encrypted traffic between an Azure virtual network and an on-premises location over the public Internet. You can also use a VPN gateway to send encrypted traffic between Azure virtual networks over the Microsoft network. Each virtual network can have only one VPN gateway. However, you can create multiple connections to the same VPN gateway. When you create multiple connections to the same VPN gateway, all VPN tunnels share the available gateway bandwidth.

>**Note:** Click [Here](https://docs.microsoft.com/en-us/azure/vpn-gateway/vpn-gateway-about-vpngateways) to check more information about the Azure VPN Gateway/Virtual Network Gateway including Design, SKUs, AZs and Pricing.

To configure the Azure VPN Gateway/Virtual Network Gateway, you need to configure the following components:

  - Azure Local Network Gateway
  - Azure Connections
  - Azure Virtual Network Gateway

Please check [Here](https://docs.microsoft.com/en-us/azure/vpn-gateway/tutorial-site-to-site-portal) if you are not familar with Azure VPN Gateway Creation. Right now, I am going to provide some examples.

Azure Local Network Gateway
<div align=left><img width = '300' src =".image/2021-01-30-15-56-44.png"/></div>

 Azure Connection
<div align=left><img width = '300' src =".image/2021-01-30-16-03-46.png"/></div>

Azure Virtual Network Gateway
<div align=left><img width = '300' src =".image/2021-01-30-16-04-12.png"/></div>

## Configure Fortigate Fortinet Firewall
