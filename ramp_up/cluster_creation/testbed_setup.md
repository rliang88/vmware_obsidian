# Testbed Setup
**About**:
This is how we would setup our testbed prior to deploying a cluster (either through CAPVCD or VCDKE).

**Important References in**: [[ramp_up/temp]]

```
brand new testbed creation -> capi dev confluence document -> run the vcd login command, create org, etc -> run the script from cse-ctot w/ updated info -> register VCDKE, CAPVCD schemas -> create VCDKE Config instance -> create users / update rights -> back to capi dev confluence document for running the commands to create a catalog / upload ubuntu ova like we did today -> install cluster creation plugin
```
1.   [CAPI dev setup](https://confluence.eng.vmware.com/pages/viewpage.action?spaceKey=VCD&title=CAPI+dev+set+up)
	- [Jenkins Preflight-4.0-STF](https://sp-taas-vcd-butler.svc.eng.vmware.com/job/Preflight-4.0-STF/)
	- creates the testbed (get the `testbed.json`) and login as system admin (provider)
	- create a test org (org1 is our test tenant)
	- Things to edit in Preflight:
		- `TESTBED_DESCRIPTOR_NAME`
		- `VCD_BUILD`
		- `owner` = my vmware email address
		- make sure `VCD_ORG_VDC` and `VCD_ORG_VDC_NETWORK` are both either VC1 or VC2
		- `ROUTABLE_IP_COUNT` = 10
2.  Run [[cse_ctot_script]]
	- This sets up the testbed with a lot of networking related configurations
3. Register VCD-KE and CAPVCD Entity Types
	- VCD-KE Config Entity Type
		- [this confluence](https://confluence.eng.vmware.com/pages/viewpage.action?pageId=1453372223)
	- CAPVCD Entity Type
		- [this confluence](https://confluence.eng.vmware.com/pages/viewpage.action?pageId=1453364827)
4.  Create Users / Update Rights
	- Configure admin rights:
		- Provider -> Administration -> Tenant Access Control -> Rights Bundle -> Edit Default Rights Bundle
			- **User** : manage user's own API Tokens
			-  **Org VDC** : create a shared disk
			- **vApps** : preseve all ExtraConfig
			- **Gateway Service** : View+Configure NAT, View+Configure Load Balancer
			- **Catalog** : View Shared Catalogs
		- SAVE, AND AFTERWARDS: PUBLISH RIGHTS BUNDLE TO ORG1
	- Configure `cluster_admin` tenant role:
		- Tenant -> Administration -> Access Control -> Roles -> Clone vApp Author
		- name it `cluster_admin` and modify selected rights
			- **Gateway** : view
			- **Gateway Service** : Configure NAT, Configure Load Balancer
			- **Catalog** : View shared catalogs from other orgs
			- **User** : Manage user's own API Tokens
			- **Org VDC** : Create a shared disk
			- **vApp** : Preserve all ExtraConfig Elements
	- Configure `service_account` role:
		- https://confluence.eng.vmware.com/display/VCD/GA+Test+Plan#GATestPlan-CSEManagementTabviaUI
			- select all VCDKECONFIG and CAPVCD options at the bottom
5.  Create catalog and upload Ubuntu OVA
	- OVA named something like:
		- `ubuntu-2004-kube-v1.21.8+vmware.1-tkg.2-ed3c93616a02968be452fe1934a1d37c.ova`
		- `~/programming_projects/vcd_training/testbed_config`
		- if you lose ova, ask Zichong
	- Run these commands:
```
vcd org use org1
vcd vdc use ovdc1
vcd catalog create cse
vcd catalog upload cse <yourPathToUbuntuOva>
```
REMEMBER TO PUBLISH CATALOG TO ALL ORGS

1. Install Cluster Creation UI Plugin
	- Find latest versions of Andrew's UI plugins [here](https://confluence.eng.vmware.com/display/VCD/UI+v4+-+Builds)
	- Disable old Container UI Plugin:
		- Provider -> more -> customize portal -> disable Container UI Plugin (probably 3.x.x)
	- Upload new container plugin zip 
	- Publish to all tenants
2. create `tanzuSmall` sizing policy