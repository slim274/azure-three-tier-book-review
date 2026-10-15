# Security and Evidence Limitations

## What the evidence supports

- **Tier separation** is recorded in the submitted Word document and reflected in the Azure VNet and subnet captures. The Word narrative states VNet `10.0.0.0/16`, but the Azure overview screenshot displays **`10.0.0.0/20`**; the deployed subnet CIDRs shown fit within `/20`.
- Azure **public and internal load balancers** are visible. The internal LB shows `10.0.4.100`, app backend pool with two VMs, and `3001` traffic.
- Azure **Database for MySQL Flexible Server** is visible with **Private access (VNet Integration)**, `bookreview-vnet/db-subnet-1`, and a private DNS zone.
- The MySQL overview shows **High availability: Enabled**, **High availability mode: Same zone**, and **Replication role: None**.
- The Book Review web interface was open in a browser when captured.

## What is reported but not independently demonstrated

The written assignment describes 'Multi-AZ' database deployment and a read replica. However, the database overview does not support either claim: the HA mode is **same zone** and replication role is **none**. Do not describe the project as having a functioning cross-zone database standby or read replica unless new Azure evidence is provided.

## Other boundaries

- Having two web VMs and two app VMs does **not** by itself establish that an availability-zone outage or loss of a VM was tested successfully.
- The displayed web listener is **HTTP/80**; HTTPS configuration or production-grade certificate management was not evidenced.
- No infrastructure-as-code, monitoring alerting, automated scaling, CI/CD pipeline or load-test results were provided in Assignment 4.
- The report does not fully document MySQL replication topology or high-availability failover testing.
- Azure Portal screenshots are **historical**. They do not prove present-day live service status.

## Publishing precautions

This documentation contains **no live database credentials, SSH private keys or token values**. Browser/tenant chrome was trimmed from screenshot images; some subscription identifiers were redacted while resource names and configuration labels were kept. Before adding **source code** to a public repository, check all tracked files and entire Git history for secrets. Only add deployment configs with placeholder values (not real `.env`, credentials, API keys or private PEMs).
