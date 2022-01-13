# tf-controller-test

```
apiVersion: source.toolkit.fluxcd.io/v1beta1
kind: GitRepository
metadata:
  name: tf-controller-test
  namespace: flux-system
spec:
  interval: 30s
  url: https://github.com/tomhuang12/tf-controller-test
  ref:
    branch: main
---
apiVersion: infra.contrib.fluxcd.io/v1alpha1
kind: Terraform
metadata:
  name: tf-controller-test-tf
  namespace: flux-system
spec:
  path: ./
  interval: 1m
  sourceRef:
    kind: GitRepository
    name: tf-controller-test
    namespace: flux-system
```