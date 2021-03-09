# Ingress

In order to expose Redis from outside the cluster, istio needs to be configured with an additional TCP ingress port.  See the istio-controlplane repo for more information on how to configure istio with a dedicated port [Here](https://repo1.dso.mil/platform-one/big-bang/apps/core/istio-controlplane/-/blob/main/chart/values.yaml#L83)


Here is a sample overlay for deploying BigBang that supports a dedicated redis TCP port at 13337:

```yaml
istio:
  values:
    ingressGateway:
      ports:
      # Existing ports for default configuration.  See note in repo about why these are still here
        - port: 15021
          targetPort: 15021
          name: status-port
          protocol: TCP
        - port: 80
          targetPort: 8080
          name: http2
          protocol: TCP
        - port: 443
          targetPort: 8443
          name: https
          protocol: TCP
        - port: 15012
          targetPort: 15012
          name: tcp-istiod
          protocol: TCP
        - port: 15443
          targetPort: 15443
          name: tls
          protocol: TCP
          # This is the extra Redis port
        - port: 13337
          name: redis-port
          protocol: TCP
```


Redis now needs a gateway dedicated to the redis port and creates one as part of the chart.  If testing locally, it may not be feasible to setup and deploy a load balancer in front of the new port, so using a terminal for port forwarding can suffice:

```bash
kubectl port-forward svc/istio-ingressgateway -n istio-system 13337:13337
Forwarding from 127.0.0.1:13337 -> 13337
Forwarding from [::1]:13337 -> 13337
```


While leaving that open, we can now use another terminal to test the connection:

```bash
❯ export REDIS_SECRET=`kubectl get secrets -n redis redis -o jsonpath='{ .data.redis-password }' | base64 --decode`
redis-cli --pass ${REDIS_SECRET} -h redis.bigbang.dev -p 13337  PING
Warning: Using a password with '-a' or '-u' option on the command line interface may not be safe.
PONG
```


If no other TCP Virtual Services are needed, the default one created at port 15443 can be used

## More Reading:

* https://stackoverflow.com/questions/59780850/how-to-expose-redis-to-outside-with-istio-sidecar
