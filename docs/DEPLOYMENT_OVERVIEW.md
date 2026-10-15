# Azure Three-Tier Deployment Overview

This describes the deployment recorded in **Week 8, Assignment 4** without reproducing assignment instructions.

## Network segmentation

The `bookreview-vnet` VNet in **UK West** contains six subnets. Its Azure overview screenshot lists address space **`10.0.0.0/20`**, whereas the written assignment describes **`10.0.0.0/16`**. The six configured subnet CIDRs fit inside the screenshot's `/20`. The subnets segment web, application and database traffic. Web subnet ranges are `10.0.0.0/23` and `10.0.2.0/23`; application subnet ranges are `10.0.4.0/23` and `10.0.6.0/23`; database subnet ranges are `10.0.8.0/23` and `10.0.10.0/23`.

## Public web access

The `web-public-lb` accepts external traffic on port `80` and forwards it to a web backend pool containing `web-vm-1` and `web-vm-2`. These instances run the Next.js interface served by Nginx. The `web-nsg` provides the web-tier inbound rules discussed in the report.

## Private backend

Requests from the web tier go to an internal Azure Load Balancer (`internal-lb`), with private frontend address **`10.0.4.100`** and TCP port **`3001`**. Its backend pool contains `app-vm-1` and `app-vm-2`, running the Node.js application. Application nodes were placed in private subnets to avoid public internet exposure. `app-nsg` restricts application traffic from the web tier.

## Database tier

Azure Database for MySQL Flexible Server (`bookdb`) was configured with **private VNet integration**, reflected in the Azure Portal screenshot. The assignment describes access from the application subnet ranges on TCP **`3306`**. The database screenshot shows **high availability enabled in Same zone mode** and **replication role None**: cross-zone HA and an operating read replica should not be claimed.

## Verification

The assignment includes evidence of the deployed VNet, subnets, NSGs, load balancers, VMs, private database configuration and a working Book Review browser interface. These are historical configuration screenshots. They are not uptime measurements, load tests or automatic-failover test results.
