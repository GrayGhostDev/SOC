# Data Storage (Time-Series Database)

## A. Select and Deploy Database

### Recommended Choices:
- InfluxDB (simple setup, robust query capability)
- Prometheus (excellent monitoring capabilities)
- TimescaleDB (Postgres-compatible)

## B. Steps for Implementation:

1. Deploy database in containerized environments (Docker/Kubernetes).
2. Define retention policies based on data size requirements.
3. Integrate normalization output into database ingestion API.