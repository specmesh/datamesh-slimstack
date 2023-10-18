# Data Mesh slimstack for SpecMesh

### The MVP for building a streaming data mesh


This demo environment uses:
- [Apacke Kafka](https://kafka.apache.org/) 
- [LinkedIn DataHub (Data catalogue)](https://datahubproject.io/)
- [ClickHouse (Viewing Kafka data)](https://datahubproject.io/)
- [Microcks (Data generation)](https://microcks.io/)
- [SpecMesh](https://specmesh.io/) for Provisioning, Governance and publishing to specs and associated schemas (and meta-data) to DataHub



Resources:
- https://microcks.io/documentation/installing/docker-compose/
- 


1. Normal mode 
```
docker-compose -f microcks-docker-compose.yml -f microcks-docker-compose-async-addon.yml up -d
```
2. DEV mode
```
docker-compose -f microcks-docker-compose-devmode.yml up -d
```

Next Steps: see https://microcks.io/blog/async-features-with-docker-compose/