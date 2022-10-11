**Namespaces**
- namespaces are a way to organize clusters into smaller sub-clusters
- arbitrary number of namespaces in a cluster
- default k8s namespaces are:
	- default: for objects with unspecified namespaces
		- 
	- kube-system: for objects created by k8s system
	- kube-public
	- kube-node-lease

**Deployment**
- A deployment is a running sub-cluster
- if changes are made to an object's yaml, we can run: `kubectl apply -f <object.yml>` to apply the changes to the deployment

**Persistent Volumes (PV) vs Persistent Volume Claims (PVC)**
- **Persistent Volumes** are a pool of storage in Kubernetes not associated with any nodes/pods
- **Persistent Volume Claims** are a request for storage to a pod by a user