# ReplicaSet
## What is a ReplicaSet?
It is a construct that runs multiple instances of the same pod

- ReplicaSet self-heals based on desired state specified in pod yml

## Labels and Selectors
**labels**: key/value pairs used to identify objects in `spec`
**selector**: used in ReplicaSet yaml to select which objects to make replicas of
- using the `matchLabels` directive

Replica Set can scale declaratively (through applying YAML) or imperatively (through) cmd interface

