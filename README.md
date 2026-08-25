# Kubernetes Engineering Lab

Hands-on Kubernetes engineering scenarios covering cluster bootstrap, security, networking, deployment strategies, stateful workloads, autoscaling, backup/restore, certificate rotation and service mesh.

## Topics

- kubeadm cluster bootstrap and recovery
- authentication and authorization
- NetworkPolicy and workload isolation
- secure and highly available applications
- controllers and operators
- StatefulSets and persistent workloads
- secrets and configuration management
- Horizontal Pod Autoscaling
- Velero backup and restore
- certificate rotation
- blue/green and canary deployments
- Istio gateway and traffic management

## Repository map

| Directory | Focus |
|---|---|
| `1.kubeadm` | bootstrap, CNI, recovery |
| `2.auth` | authentication / RBAC |
| `3.network policies` | network segmentation |
| `4.secure-and-highlyavailable-apps` | resilient workloads |
| `5.controllers-and-operators` | controllers/operators |
| `6.stateful` | stateful workloads |
| `7.secret` | secrets |
| `8.hpa` | autoscaling |
| `9.heptio_velero` | backup and restore |
| `10.certificate_rotate` | PKI / certificate lifecycle |
| `11.deploy` | deployment strategies |
| `12.istio` | service mesh |

## Engineering focus

The repository originated as hands-on training material and is retained as an engineering lab. The value is in reproducible manifests and operational scenarios: cluster lifecycle, failure recovery, deployment safety and platform behavior.

## Validation

A GitHub Actions workflow performs YAML syntax checks for lightweight validation. Some historical manifests target older Kubernetes/Istio versions, so compatibility with modern clusters should be reviewed before applying them directly.

## Portfolio note

For a production-style end-to-end GitOps project with reusable Helm charts and Argo CD, see `Evgenz-mr/gitops-lab`.
