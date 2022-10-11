VCD URI:
```
https://atl1-vcd-static-133-89.eng.vmware.com
```

API Endpoints
```REST
# LOGIN - POST
/api/login

# 
```

VCD Build Version
```
v10.3.3
ob-19858287
```

ssh key:
```
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABgQC17UNYmk1BUYrdXWvYpSEQV+H/FPJWHnLcLgvcObIegyzRY3kSd3LxkZUhyOgk4hIlvy9Z55BIVpnvD3WFuoDF7+f7ceSvYeptNQT/7676xGEJEoLw33qHHNzReKRgX1UO/UVwCFAlJ3XBrIM58c1moY9RFTVTvf0rOyKETpT//Rvna7OXrCobFR2Z0MD6Wg3bIkZ5KTqrHJJPXdx/r6T5KbrJjtqYojH9TUjxxzXIhHdqUFBYCh7CfDyQ/nGcY4kdYeul4itRNF5qd6bMdegIqDCjBnGhHKY4LBoA+0HJa+neg5GurG+OyMSoTrrhmagwQWQ3bb/h7jvO9Rf9/60ncrsYF3/bJp5CezS0ynbdGL9A/zMx1yAapk4n9zh/JZCyd9pLuX1fNt3XQ9Lj4ByWDwhVf2NyfPD/QKUzp5yJ/wG5OPR4I+WAMcmzauBQwkhWmxl4XRlbRyBgpyh4IABQDkBBTGnoMHinyNmni9J2MKi+ZtI4ksN2LxhuTHLTZt8= rliang@rliang-a01.vmware.com
```

API endpoint to get RDE ID to access capiyaml
```
https://atl1-vcd-static-101-207.eng.vmware.com/cloudapi/1.0.0/entities/types/vmware/capvcdCluster/1.1.0
```

bearer token:
```
eyJhbGciOiJSUzI1NiJ9.eyJzdWIiOiJhZG1pbmlzdHJhdG9yIiwiaXNzIjoiYTkzYzlkYjktNzQ3MS0zMTkyLThkMDktYThmN2VlZGE4NWY5QDA4MzA4MDA5LTk3YTItNGZhMy1hYWVhLWNjYjdiZTM3MjM0NCIsImV4cCI6MTY2NDEyODEwNiwidmVyc2lvbiI6InZjbG91ZF8xLjAiLCJqdGkiOiIyNDQ3ODk5MWU4MDE0NTM3ODQxODEyODMwNzY5YjI2MCJ9.mSbx1oomQyqDl6dnVlnU1FzwWKvalcdSwzvYJO_vPurNR4jJ9JsU9rmlLwqnmle30KxpWsYnn3MRsVMkqsaKW07GjrLnl-Gwoo-3DC6DFG1KlKZEZA9RaZmA5EgbSHlKqGIDuPq19GsnMjzhzOLx3uy60K2ti2VW5RmJ_YqZZ2VjaRpHHcUgCouFuXEXamElN8XGUvRErT6dskssJ90lefYK53pWJQceoVvDaBiyxkGYtn7qk-YLlbxoD_Q6YSiN5cm45_boINdyNP8BTQSTGynFSy_LgL_i5lKvKCUApT9RpVmvUIhIOU6PDSrhfFwN1Nl3XrzmspRZaCY0QdqXEw
```

API endpoint to update capiyaml in RDE
```
https://atl1-vcd-static-101-207.eng.vmware.com/cloudapi/1.0.0/entities/urn:vcloud:entity:vmware:capvcdCluster:00e667f4-f8d6-4aec-bc58-102c2382f10f
```

To destroy a cluster, first:
send a PUT request to: first api endpoint above with the following changes
```
# CASE SENSITIVE
# will have to add this property
entity.spec.autoRepairOnErrors = true
status.vcdkestate = "provisioned"
```

Rights for cluster admin:
```
- Provider (head admin)
    Rights:
        Update Default Rights Bundle
        User -> Manage API Tokens
        Org VDC -> Create a Shared Disk
        vApps -> Preserve All Extra Config
        Gateway Service -> View/Configure NAT, Loadbalancer
        Catalog -> View Shared Catalogs
    Publish Rights Bundles after updating (anytime we add new things such as VKPConfig, CAPVCD Clusters)
    
- Tenant (users)
    Rights:
        Clone vApp Author -> Modify Selected Rights
                View/Full Control/Edit CSE, CAPVCD, etc
            Gateway -> View
            Gateway Service -> Load Balancer, NAT Configure
            Catalog -> View shared catalogs from other orgs
            User -> Manage user's own API Tokens
            Org VDC -> Create a shared Disk
            vApp -> Preserve all extra config elements
```

To access vCenter:
```
Provider -> 
```

10.89.99.211 - 10.89.99.213  
  
10.89.99.174 - 10.89.99.174  
  
10.89.99.206 - 10.89.99.207

---

10.89.99.177-10.89.99.177
10.89.99.204-10.89.99.204
10.89.99.208-10.89.99.208
10.89.99.224-10.89.99.224

left off at adding external IPs to solution org tier-0 gateway