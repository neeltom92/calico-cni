# calico-cni

- installation steps:
https://www.eksworkshop.com/beginner/120_network-policies/calico/install_calico/

- this is pretty useful only in 2 cases
- stage and prod are in same namespace
- DB to pod app communication

- here we are trying to achieve namespace scoped isolation.
  * we have two namespace prodarcab and production
  * we dont want to communicate from production to prodarcab
- manifest file allow.yaml
- if applied it will block all traffic all pods !
- for production to prodarcab work u need to label that production with label " role: production"
- kubectl label namespace/production role=production
- so ensure that all namespaces that needs to communicate to prodarcab be labelled


refer:

- https://www.eksworkshop.com/beginner/120_network-policies/calico/install_calico/
- https://stackoverflow.com/questions/50807579/whitelist-kube-system-namespace-using-networkpolicy
- https://projectcalico.docs.tigera.io/reference/resources/globalnetworkpolicy
