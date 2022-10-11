# [`cse-ctot`](https://gitlab.eng.vmware.com/akrishnakuma/cse-ctot) script to run for testbed setup
**About CSE-ctot**: sets up the testbed with lots of networking related configurations
- clone the repo in the title
- `cd` into the repo
- run:
```zsh
# ------------------
# THINGS TO MODIFY
#
# vcd-host URL : change to endPointURI from testbed.json
#
# ovdc : don't need to change if copied script from confluence 
#
# tier0-cidr : gateway IP of testbed from Cassini.
# Access this: details button (in testbed vApp) -> Networks -> Gateway CIDR
#
# external-ip-range : give one of the ranges of the routable IPs. We will add
# the others later in the VCD webapp
# ------------------
  

go run cmd/main.go network routed create \
--vcd-host="https://atl1-vcd-static-101-207.eng.vmware.com" \
--org=org1 \
--ovdc=ovdc1 \
--external-tier0-nw="external_tier0_nw" \
--edge-gateway="tenant1_edge_gw" \
--tier0-cidr="10.89.127.253/19" \
--external-ip-range="10.89.101.209-10.89.101.211" \
--routed-ovdc-nw=ovdc1_nw \
--tier1-cidr="192.168.7.1/24" \
--internal-ip-range="192.168.7.2-192.168.7.100" \
--tier1-subnet="192.168.7.0/24" \
--enable-avi


%%TEMP%%

go run cmd/main.go network routed create \
--vcd-host="https://atl1-vcd-static-131-33.eng.vmware.com" \
--org=org1 \
--ovdc=ovdc1 \
--external-tier0-nw="external_tier0_nw" \
--edge-gateway="tenant1_edge_gw" \
--tier0-cidr="10.89.159.253/19" \
--external-ip-range="10.89.131.110-10.89.131.113" \
--routed-ovdc-nw=ovdc1_nw \
--tier1-cidr="192.168.7.1/24" \
--internal-ip-range="192.168.7.2-192.168.7.100" \
--tier1-subnet="192.168.7.0/24" \
--enable-avi
```