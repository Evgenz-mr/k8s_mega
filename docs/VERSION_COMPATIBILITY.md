# Kubernetes version compatibility guide

This repository intentionally contains historical manifests and exercises created across different Kubernetes generations. Treat API/version compatibility as part of the exercise.

## Before applying a lab

1. Check every `apiVersion` against the target cluster minor version.
2. Replace removed beta APIs before deployment.
3. Review Pod Security changes; PodSecurityPolicy is removed from modern Kubernetes.
4. Verify ingress-controller annotations and Ingress API fields.
5. Check CNI manifests against the intended Kubernetes release rather than applying archived vendor YAML blindly.
6. Review certificate rotation and kubeadm commands against the installed kubeadm version.
7. Verify Istio examples against the installed Istio API/version.

## Historical API examples to look for

- `extensions/v1beta1`
- `apps/v1beta1` / `apps/v1beta2`
- `policy/v1beta1`
- `PodSecurityPolicy`

Their presence in this repository can be useful for migration exercises, but they must not be presented as current production defaults.

## Recommended workflow

```text
historical manifest
      |
      v
identify removed/deprecated API
      |
      v
rewrite to current API
      |
      v
schema validation
      |
      v
ephemeral cluster test
```
