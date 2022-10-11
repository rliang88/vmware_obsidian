# Temp
## VCDA 4473
- https://cluster-api.sigs.k8s.io/clusterctl/provider-contract.html#move
- the labels `clusterctl.cluster.x-k8s.io/move=""` and `clusterctl.cluster.x-k8s.io=""` are required to let `clusterctl` know which entities are to be moved in a `clusterctl move` operation

## VCDA 4536
- In VCDKE
- there is an api to modify RDE with code
	- `rdeUtils.go -> PatchRDE()`
		- uses `PatchRDEOnce()` as helper method
			- uses `PatchObject()` and passes in `capvcdEntity.Spec`
- In `types.go`:
	- `CAPVCDEntity.Spec` -> `CAPVCDSpec`
		- `CAPVCDSpec` does not have `VCDKESpec` in it, so had to add it ourselves
		- Because of no `VCDKESpec`, `VCDKESpec` was unable to be marshalled here:
			- `capvcdEntity, err := util.ConvertMapToCAPVCDEntity(rde.Entity)`

- when there is new code in upstream/main
- 