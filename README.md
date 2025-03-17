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

