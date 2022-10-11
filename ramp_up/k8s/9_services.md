# Services
**Services Definition** - an abstract way to expose an application running on pods via an endpoint

**Types of Services**
- ClusterIP
- NodePort
- LoadBalancer

- Pods are ephemeral (disposable)
- Services are persistent

## ClusterIP
- **definition**
	- internal fixed IP used for pod-to-pod communication
	- load balanced IP
		- requests will load balanced across pod replicas

## NodePort
- **definition**
	- a service used for when an external client (customer) wants to access the application hosted on k8s
	- uses ClusterIP in the background
	- accessed by outside through `<NodeIP>:<NodePort>`

## Load Balancer
- **definition**
	- I already know what a LB is
	- stream of incoming requests into an application is split amongst replicas to decrease service time