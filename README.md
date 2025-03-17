# Streams for Apache Kafka GitOps K-Raft Upgrade

## Initial Bootstrap

1. Install ArgoCD

```
oc apply -k argocd/bootstrap/operator
```

2. Configure ArgoCD instance

```
oc apply -k argocd/bootstrap/instance
```

3. Deploy Kafka

```
oc apply -f argocd/kafka.yaml
```

## K-Raft Upgrade

Follow [Migrating to K-Raft](https://docs.redhat.com/en/documentation/red_hat_streams_for_apache_kafka/2.9/html/deploying_and_managing_streams_for_apache_kafka_on_openshift/assembly-kraft-mode-str#proc-deploy-migrate-kraft-str) from Red Hat Streams for Apache Kafka documentation.

For a sample of GitOps commits that perform the K-Raft upgrade, you can view a diff between the `main` branch of this repository and the `k-raft` branch.

### Important to note:

- Upgrading to K-Raft will require `KafkaNodePools`, if they are not enabled, the first step is to enable them.
- You cannot have ZooKeeper `jbod` volumes that are composed of more than one disk array.
- You must have capacity to support ZooKeeper and Kafka Controller nodes at the same time during the upgrade.