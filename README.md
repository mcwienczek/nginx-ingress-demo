# Ingress wildcard demo

This repository shows how can you break Nginx Ingress Controller by passing Kubernetes ingress validation that is not correct form Nginx Ingress Controller perspective. 

The full description is available at: https://cwienczek.com/

To reproduce the issue:

1. Change ingress hostname inside both ingress YAML files
2. Deploy everything except ingress-broken.yaml using kubectl to your cluster
3. Update ingress definition to ingress-broken.yaml
4. run `kubectl logs` on Nginx Ingress Controller pod to see how it failed to update it's configuration. 

At this point cluster won't accept any new ingress definitions until you delete the faulty ingress.
