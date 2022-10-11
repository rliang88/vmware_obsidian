- kinda like config maps
- secrets are stored unencrypted in the API server, in etcd
- anyone who has access to the API server can change a secret

**2 steps for secrets**
	1. create secret
	2. inject the secrect into pods

