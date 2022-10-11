- User for cluster-org is created in cluster-org tenant page (as provider)
- CSE service account created in provider side

- create cluster in Solution Org by logging into provider and going into Solution Org portal

- To update a project's vendor package:
	1. `go get -u <github.com/vmware/project>@<commit hash>`
	2. `make vendor`

- To get IP subnet
	- `tenant -> networking -> edge gateways -> IP Allocation -> IP Block`

- Administrator in Tenant:
	- user = administrator
	- userorg = system
	- password = ca$hc0w