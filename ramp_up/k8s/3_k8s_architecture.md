# K8s Architecture
## High Level:
- k8s consists of master node (control plane) and worker nodes
- **Master node**:
	- `kube-apiserver` 
		- client entrypoint into k8s cluster
		- validates requests nad orchestrates all operations in cluster
		- THE BRAIN
	- `kube-scheduler` = assigns pods to the correct nodes
	- `kube-controller-manager`
		- daemon that installs core control loops 
			- control loop: non-terminating loop that regulates state of the cluster
	- `etcd` = key | value store containing info about the cluster
		- ex: resource availability, backups of cluster state
- **Worker node**: instance of a single or multi-container application
	- Pods = individual containers (the workload)
	- Kubelet = agent that communicates w `kube-apiserver` in the master node
	- kube-proxy = network proxy that enables networking for the pods
		- pods in the node interact with kube-proxy for networking between other nodes' pods or external traffic