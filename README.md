# Helm Chart for Harbor

원본은 [goharbor/harbor](https://github.com/goharbor/harbor)에 있습니다. 자세한 설정내용은 원본을 참조하세요.

## Introduction

Harbor를 위한 Helm Chart 입니다.

## Prerequisites

- Kubernetes cluster 1.10+
- Helm 2.8.0+

## Installation

### Add Helm repository

```bash
helm repo add harbor https://helm.goharbor.io
```

### Configure the chart

The following items can be set via `--set` flag during installation or configured by editing the `values.yaml` directly(need to download the chart first).

### Install the chart

helm install 이전에 pv_pvc.yaml을 apply 하여 registry, chartmuseum, jobservice, database, redis, trivy 의 volume을 생성해줍니다.

helm 3:
```bash
kubectl apply -f harbor-helm/pv_pvc.yaml
helm install yellow harbor-helm/ -n harbor
```

## Uninstallation

To uninstall/delete the `my-release` deployment:

helm 3:
```
helm uninstall my-release
```
