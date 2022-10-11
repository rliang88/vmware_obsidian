# [VCD Admin Portal Guide](https://docs.vmware.com/en/VMware-Cloud-Director/10.3/VMware-Cloud-Director-Service-Provider-Admin-Portal-Guide/GUID-F8F4B534-49B2-43B2-AEEE-7BAEE8CE1844.html)
- VCD is an interface for public cloud service providers

## Overview of VCD Administration
- VCD uses vSphere and NSX to power VMs
	- [[ramp_up/notes#^5fa0ac|vSphere and vCenter]]
- **Cloud Resources** = vSphere and NSX resources
	- number of CPUs and RAM
- **vApp** = virtual system consisting of 1+ VCD VMs
- **Provider VDC (PVDC)** = combines compute and memory resources of one vCenter Server
	- AKA an instance of vSphere
- **Organization VDC (OVDC)** = VDC for use by an organization
	- partitioned from a Provider Virtual Data Center
	- a smaller vSphere partitioned from PVDC
- [[vcd_networking|VCD Networking]]

## Managing Infrastructure Resources
- SDDCs are backed by vCenter Server