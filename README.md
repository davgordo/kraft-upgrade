# Streams for Apache Kafka GitOps K-Raft Upgrade

## Initial Bootstrap

1. Install ArgoCD

```
oc apply -f argocd/bootstrap
```

2. Configure ArgoCD instance

```
oc apply -f argocd/instance
```

3. Deploy Kafka

```
oc apply -f argocd/kafka.yaml
```

## K-Raft Upgrade

