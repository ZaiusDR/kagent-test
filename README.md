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

## Configuration

### Ollama Model

The default model is set to `qwen2.5-coder:7b` in `helm/kagent-ollama/values.yaml`. You can change this by updating the `ollamaModel` value.

```yaml
ollamaModel: &ollamaModel "llama3.2"
```

## Kagent Setup

### Install Kagent CRDs

```bash
helm install kagent-crds oci://ghcr.io/kagent-dev/kagent/helm/kagent-crds
```

### Install Kagent Helm Chart

```bash
helm install kagent helm/kagent-ollama --namespace kagent --create-namespace
```

### Uninstall Kagent

```bash
helm uninstall kagent --namespace kagent
```
