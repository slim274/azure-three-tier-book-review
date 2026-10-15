# Troubleshooting and Resolutions

These issues and resolutions are paraphrased from the **Week 8, Assignment 4** report. Do not mistake them for reproducible logs or proofs of a full resilience test.

### Subnet sizing
**Issue:** Determining the right subnet sizes for a three-tier Azure network.
**Action taken:** Calculated and applied six non-overlapping `/23` address ranges. The source text says the VNet uses `/16`; the portal screenshot shows `/20`, a space sufficient for the six captured ranges.

### Backend pool membership
**Issue:** Difficulty connecting VMs to the correct load balancer backend pools.
**Action taken:** Associated `web-vm-1` and `web-vm-2` with `web-public-lb`, and `app-vm-1` and `app-vm-2` with the `internal-lb` app backend pool.

### Backend internet exposure
**Issue:** Keeping Node.js application VMs private while routing user traffic from the public website.
**Action taken:** Used private app subnets and the internal load balancer instead of publicly addressing application VMs.

### MySQL connection denied
**Issue:** Node.js app-tier connectivity to MySQL was blocked by security-group / subnet controls.
**Action taken:** Added `db-nsg` inbound permission for port `3306` from `app-subnet-1` and `app-subnet-2`. The report says the backend connected afterward; no production-credential details are included here.
