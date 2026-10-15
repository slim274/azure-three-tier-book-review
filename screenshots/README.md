# Screenshot evidence — Week 8, Assignment 4

These are **original embedded screenshots from Word (.docx)** (not PDF page crops), preserved near 1,900 pixels wide. Browser/tenant headers were removed and only specific subscription/resource identifiers were masked for safe publication. Screenshot settings such as the MySQL connectivity method, HA mode, LB private address and backend pools have been preserved.

| File | What it shows |
|---|---|
| [01-azure-virtual-network.png](01-azure-virtual-network.png) | Azure VNet overview (`bookreview-vnet`, UK West, six subnets) |
| [02-six-subnets.png](02-six-subnets.png) | VNet subnet list (web, app and database subnet ranges) |
| [03-network-security-groups.png](03-network-security-groups.png) | Network security groups overview |
| [04-web-nsg.png](04-web-nsg.png) | Web network security group rules |
| [05-app-nsg.png](05-app-nsg.png) | Application network security group rules |
| [06-db-nsg.png](06-db-nsg.png) | Database network security group rules |
| [07-public-load-balancer.png](07-public-load-balancer.png) | Public load balancer (`web-public-lb`) overview |
| [08-internal-load-balancer.png](08-internal-load-balancer.png) | Internal load balancer (`internal-lb`), private IP `10.0.4.100`, app backend pool |
| [09-virtual-machines.png](09-virtual-machines.png) | Azure virtual machines list, including web and application instances |
| [10-web-vm-networking.png](10-web-vm-networking.png) | Web VM network settings |
| [11-app-vm-networking.png](11-app-vm-networking.png) | Application VM network settings |
| [12-azure-mysql-overview.png](12-azure-mysql-overview.png) | MySQL Flexible Server `bookdb` overview: private VNet access and same-zone HA |
| [13-book-review-application.png](13-book-review-application.png) | Running Book Review application UI |


The screenshots represent a particular stage in the lab. Do not interpret them as proof the resources remain live or that disaster recovery and high-availability scenarios were tested. The database screenshot shows **private access**, **same-zone HA**, and **replication role None**. **No read replica is verified.**
