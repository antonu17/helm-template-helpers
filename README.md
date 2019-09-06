# Global variables in template helpers

## Experiment

```shell
git clone https://github.com/antonu17/helm-template-helpers.git
cd helm-template-helpers
helm template chart
---
# Source: chart/templates/test_global.yaml
1. Output "$uuid":
5cb9d884-bcb2-44b2-8de2-d3d8cf1dd9c1

2. Output "$uuid":
5cb9d884-bcb2-44b2-8de2-d3d8cf1dd9c1

---
# Source: chart/templates/test_helper.yaml
1. Include helper "chart.test":
a84e0756-1238-4822-96bd-f953a789d37d

2. Include helper "chart.test":
240a8659-f8b0-48f0-965e-daa32fc83b93
```

## Desired behaviour

The `{{ include "chart.test" . }}` returns the same uuid throughout the same `helm template` execution no matters how many times it is refered.
