# This is a part of Fluxcd mutli-tenancy demo with Linkerd and Flagger

Demo repository for managing a multi-tenant cluster with Flux and Kustomize,
part of [Fluxcd with Linkerd and Flagger](https://github.com/olafkfreund/K8s-fluxcd).

This repository uses [GitHub Actions](https://github.com/marketplace/actions/kubernetes-toolset)
to validate the Kubernetes manifests with kubeval and a set of Open Policy Agent
[rego rules](https://github.com/olafkfreund/K8s-team1/blob/master/.github/policy/).

GitHub [workflow](https://github.com/olafkfreund/K8s-team1/blob/master/.github/workflows/test.yml):
* validate kustomize build with kubeval strict mode
* deny containers with latest image tag
* deny deployments and services without app label selector
* warn if deployments have no prometheus pod annotations
