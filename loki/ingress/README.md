# Loki Ingress Component

To provide a cohesive [Loki API](https://grafana.com/docs/loki/latest/api/) HTTP-level routing is required to the various microservice components.

This [`kustomize` component](https://kubectl.docs.kubernetes.io/guides/config_management/components/) adds an [`Ingress`](https://kubernetes.io/docs/concepts/services-networking/ingress/) that does that routing.


## Usage

It is likely that you will want to patch the `Ingress`:

  - to only match on a specific host
  - to use an *internal* ingress controller

Because of the security implications when *not* providing such a patch, this `Ingress` is packaged as an opt-in component.
