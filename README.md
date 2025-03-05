# cluster-linking-dr

Disaster Recovery Scenario using Cluster Linking

## Start the two clusters

```bash
docker compose up -d
```

## Cluster A

```bash
docker compose exec broker-a kafka-cluster cluster-id --bootstrap-server localhost:9091
```

This should give us:

```bash
Cluster ID: AWe3nnZwTrKSM0aM2doAxQ
```




## Troubleshooting

```bash
docker compose exec broker-a bash
```

