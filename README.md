# promethues-kustomize-base
A Kustomize base for Prometheus operator and some useful exporters

## Usage

You can reference the bases in your overlays like below:
```yaml
apiVersion: kustomize.config.k8s.io/v1beta1
kind: Kustomization
resources:
- git::https://github.com/meggieveggie/promethues-kustomize-base.git/base/prometheus/
- git::https://github.com/meggieveggie/promethues-kustomize-base.git/base/prometheus-operator/
```
