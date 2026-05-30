# k8s-zero-downtime-deploy

Kubernetes deployment configurations and Helm charts for zero-downtime rolling updates, blue-green deployments, and production-grade workload management.

Built and maintained by [Barry O Young](https://github.com/bazdev0001) — DevOps engineer and open source contributor.

## Overview

This repository provides battle-tested Kubernetes deployment patterns that ensure zero downtime during application updates. Includes Helm charts, readiness/liveness probe configurations, and PodDisruptionBudget examples.

## Features

- Rolling update strategies with configurable `maxSurge` and `maxUnavailable`
- Blue-green deployment support via Helm chart parameters
- PodDisruptionBudgets for safe node draining
- Readiness and liveness probe templates
- Resource requests/limits best practices
- Horizontal Pod Autoscaler (HPA) configurations
- Pre-configured for common workloads (web APIs, workers, cron jobs)

## Usage

### Install with Helm

```bash
helm repo add barry-k8s https://bazdev0001.github.io/k8s-zero-downtime-deploy
helm install my-app barry-k8s/zero-downtime-deploy -f values.yaml
```

### Override values

```yaml
# values.yaml
replicaCount: 3

strategy:
  type: RollingUpdate
  rollingUpdate:
    maxSurge: 1
    maxUnavailable: 0

readinessProbe:
  httpGet:
    path: /health
    port: 8080
  initialDelaySeconds: 5
  periodSeconds: 10

podDisruptionBudget:
  enabled: true
  minAvailable: 2
```

## Structure

```
charts/
  templates/
    deployment.yaml
    service.yaml
    hpa.yaml
    pdb.yaml
```

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## License

Apache 2.0
