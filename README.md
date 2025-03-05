# Cluster Linking with Disaster Recovery

Disaster Recovery Scenario using Cluster Linking

## Start the two clusters

```bash
docker compose up -d
```

## Sanity Check - Cluster A

Get the Cluster ID:

```bash
docker compose exec broker-a kafka-cluster cluster-id --bootstrap-server localhost:9091
```

This should give us:

```bash
Cluster ID: AWe3nnZwTrKSM0aM2doAxQ
```

Test the console Producer to write to a given topic:

```bash
docker compose exec broker-a kafka-console-producer --bootstrap-server localhost:9091 --topic kafka-topic
```

Consume from the test topic:

```bash
docker compose exec broker-a kafka-console-consumer --bootstrap-server localhost:9091 --from-beginning --topic kafka-topic
```

## Sanity Check - Cluster B

Get the Cluster ID:

```bash
docker compose exec broker-b kafka-cluster cluster-id --bootstrap-server localhost:9092
```

This should give us:

```bash
Cluster ID: ZWe3nnZwTrKSM0aM2doAxQ
```

Test the console Producer to write to a given topic:

```bash
docker compose exec broker-b kafka-console-producer --bootstrap-server localhost:9092 --topic kafka-topic
```

Consume from the test topic:

```bash
docker compose exec broker-b kafka-console-consumer --bootstrap-server localhost:9092 --from-beginning --topic kafka-topic
```

## Troubleshooting

```bash
docker compose exec broker-a bash
```

