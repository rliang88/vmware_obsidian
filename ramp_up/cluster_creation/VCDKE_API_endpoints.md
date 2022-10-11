# Testbed VCDKE API Endpoints
## General
**Interfaces**
`{{testbed_uri}}/cloudapi/1.0.0/entityTypes`
- Methods: GET, POST
- register VCDKEConfig interface

**Entity Types**
`{{testbed_uri}}/cloudapi/1.0.0/entityTypes`
- Methods: GET, POST
- register VCDKEConfig Entity Type
- register CAPVCD RDE Schema (Entity Type)

## VCDKEConfig
**Get VCDKEConfig Instances**
`{{testbed_uri}}/cloudapi/1.0.0/entities/types/vmware/capvcdCluster/1.1.0`
- methods: GET

**Get a specific VCDKEConfig Instance**
`{{testbed_uri}}/cloudapi/1.0.0/entities/{{VCDKEConfig_id}}`
- methods : GET
- variables: `{{VCDKEConfig_id}}`

**Resolve VCDKEConfig Instance**
`{{testbed_uri}}/cloudapi/1.0.0/entities/{{VCDKEConfig_id}}/resolve`
- methods: POST
- variables: `{{VCDKEConfig_id}}`

## CAPVCD
**Get all CAPVCD Clusters**
