# Contributing to k8s-zero-downtime-deploy

Thank you for your interest in contributing!

## Maintainer

This project is maintained by **Barry O Young** ([@bazdev0001](https://github.com/bazdev0001)).
For questions or issues, open a GitHub issue or reach out via GitHub.

## How to Contribute

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/your-feature`
3. Make your changes — test Helm charts with `helm lint` and `helm template`
4. Commit with a clear conventional commit message
5. Open a pull request against `main`

## Testing Helm Charts

```bash
# Lint all charts
helm lint charts/*

# Render templates locally
helm template test charts/zero-downtime-deploy -f charts/zero-downtime-deploy/values.yaml

# Dry-run against a cluster
helm install --dry-run my-app charts/zero-downtime-deploy
```

## Reporting Bugs

Open a GitHub issue with:
- Kubernetes version
- Helm version
- Chart values used
- Error output

## Pull Request Guidelines

- Keep PRs focused — one feature or fix per PR
- Bump chart version in `Chart.yaml` for any chart changes
- Update values documentation if new parameters are added

All contributions are reviewed by Barry O Young before merging.
