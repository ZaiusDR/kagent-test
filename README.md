# kagent-test
Testing env for Kagent

## Kind Cluster

### Create Cluster

```bash
kind create cluster --config kind-config.yaml
```

### Delete Cluster

```bash
kind delete cluster --name kagent-cluster
```

## Kagent Setup

### Install Kagent CRDs

```bash
helm install kagent-crds oci://ghcr.io/kagent-dev/kagent/helm/kagent-crds \
    --namespace kagent \
    --create-namespace
```

### Install Kagent Helm Chart

```bash
helm install kagent helm/kagent-ollama --namespace kagent
```
