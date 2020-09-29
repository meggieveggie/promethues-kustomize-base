# promethues-kustomize-base
A Kustomize base for Prometheus operator and some useful exporters

## Usage

If you are installing the prometheus operator you would need to install the CRDS:

```
OPERATOR_VERSION=0.42
BASE_URL=https://raw.githubusercontent.com/prometheus-operator/prometheus-operator
kubectl apply -f ${BASE_URL}/release-${OPERATOR_VERSION}/example/prometheus-operator-crd/monitoring.coreos.com_alertmanagers.yaml
kubectl apply -f ${BASE_URL}/release-${OPERATOR_VERSION}/example/prometheus-operator-crd/monitoring.coreos.com_podmonitors.yaml 
kubectl apply -f ${BASE_URL}/release-${OPERATOR_VERSION}/example/prometheus-operator-crd/monitoring.coreos.com_prometheuses.yaml 
kubectl apply -f ${BASE_URL}/release-${OPERATOR_VERSION}/example/prometheus-operator-crd/monitoring.coreos.com_prometheusrules.yaml 
kubectl apply -f ${BASE_URL}/release-${OPERATOR_VERSION}/example/prometheus-operator-crd/monitoring.coreos.com_servicemonitors.yaml 
kubectl apply -f ${BASE_URL}/release-${OPERATOR_VERSION}/example/prometheus-operator-crd/monitoring.coreos.com_thanosrulers.yaml
kubectl apply -f ${BASE_URL}/release-${OPERATOR_VERSION}/example/prometheus-operator-crd/monitoring.coreos.com_probes.yaml
```

You can reference the bases in your overlays like below:
```yaml
apiVersion: kustomize.config.k8s.io/v1beta1
kind: Kustomization
resources:
- git::https://github.com/meggieveggie/promethues-kustomize-base.git/base/prometheus/
- git::https://github.com/meggieveggie/promethues-kustomize-base.git/base/prometheus-operator/
``

**Note:** Currently the Prometheus Instance will be created in the default Namespace 
