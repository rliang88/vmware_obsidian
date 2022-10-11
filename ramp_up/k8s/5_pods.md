# Pods
**Pods**: smallest object you can create in k8s
- pods can contain multiple tightly-coupled containers
- decalrative configs defined using `yaml`

ex:
```yml
apiVersion: v1 #version of object API
kind: Pod # type of object
metadata: # metadata, ex. name of object, namespace
	name: redis_pod
	namespace: default
spec: # additional info about pods
	containers:
	- name: redis_app_container
	  image: redis
```

## Pod commands with  `kubectl`
Create a pod from a YML pod config file:
- `kubectl create -f pod_yml.yml`

get pods:
- `kubectl get pods` 
	- get pods from only default namespace
- `kubectl get pods -A`
	- get pods from all namespaces
- `kubectl get pod <pod-name> -o yaml <path-to-yaml`
	- output declarative yaml of pod

describe a pod (AKA see pod details):
- `kubectl describe pod <pod-name>

create and run a single pod:
- `kubectl run <pod-name> --image=<image name>`
