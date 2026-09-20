# Kyverno Enterprise Policies Chart

This Helm chart deploys a categorized suite of Kyverno ClusterPolicies. It is designed to be highly customizable via `values.yaml`, allowing administrators to toggle policies on/off and set dynamic parameters for HPA generation, label enforcement, and security baselines.

## Installation
```bash
helm install kyverno-policies ./kyverno-policies-chart -n kyverno --create-namespace