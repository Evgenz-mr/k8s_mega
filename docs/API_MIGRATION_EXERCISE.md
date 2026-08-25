# Kubernetes API migration exercise

This repository contains historical manifests that are useful for practicing API migrations.

## Exercise workflow

1. Find manifests using removed or deprecated API families.
2. Identify the target Kubernetes version.
3. Rewrite the resource to the supported API.
4. Compare required fields and changed defaults.
5. Validate the result with a schema-aware tool or disposable cluster.
6. Document behavioral changes, not only syntax changes.

## Example review areas

### Ingress

Historical `extensions/v1beta1` or `networking.k8s.io/v1beta1` Ingress resources should be migrated to `networking.k8s.io/v1`, including `pathType` and the current service backend structure.

### Pod security

`PodSecurityPolicy` is removed. A modern review should consider Pod Security Admission, namespace labels, workload security contexts and policy engines where required.

### Workload APIs

Old Deployment/StatefulSet beta APIs should be migrated to `apps/v1`, with selectors explicitly matching pod-template labels.

## Portfolio goal

The useful Senior-level signal is not that historical YAML exists; it is the ability to identify why it no longer applies, migrate it safely and explain the operational consequence of the change.
