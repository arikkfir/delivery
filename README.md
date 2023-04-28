# delivery

Delivery-as-Code for my infrastructure.

#### References

- [Config Connector Reference](https://cloud.google.com/config-connector/docs/reference/overview)
- [Config Connector CRDs](https://github.com/GoogleCloudPlatform/k8s-config-connector/tree/master/crds)
- [GKE Monitoring CRDs](https://github.com/GoogleCloudPlatform/prometheus-engine/tree/main/cmd/operator/deploy/crds)

## ROADMAP

- [x] Deploy [ARC](https://github.com/actions/actions-runner-controller)
- [x] Add a FluxCD webhook to trigger a delivery
- [x] ~~Considers replacing Traefik with Ambassador~~
  - Because it supports TLS termination for non-HTTP traffic (e.g. NATS, Neo4j, Redis)
  - See https://www.getambassador.io/docs/emissary/latest/topics/using/tcpmappings
- [x] Use [Kustomization substitutions](https://fluxcd.io/flux/components/kustomize/kustomization/#post-build-variable-substitution) instead of patches where appropriate
- [ ] Install [Weaveworks GitOps](https://docs.gitops.weave.works/)
- [x] Expose Neo4j, Redis, NATS services externally
    - [x] Expose additional ports in Traefik ingress service
    - [x] Route TCP traffic based on ports to the core Neo4j, Redis, NATS `Service`
