# Ingress

In order to expose Redis from outside the cluster, istio needs to be configured with an additional TCP ingress port.  See the istio-controlplane repo for more information on how to configure istio with a dedicated port [Here](https://repo1.dso.mil/platform-one/big-bang/apps/core/istio-controlplane/-/blob/main/chart/values.yaml#L83)











More Reading:

* https://stackoverflow.com/questions/59780850/how-to-expose-redis-to-outside-with-istio-sidecar
* 