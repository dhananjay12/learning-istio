# Learning Istio

## How to Install Istio

Download istio and put it in your path - [https://istio.io/latest/docs/setup/getting-started/#download](https://istio.io/latest/docs/setup/getting-started/#download)

Install istio using `istioctl` and a [profile](https://istio.io/latest/docs/setup/additional-setup/config-profiles/) if required:
```
istioctl install --set profile=demo
```
Add a namespace label to instruct Istio to automatically inject Envoy sidecar proxies when you deploy
your application later:
```
kubectl label namespace default istio-injection=enabled
```

## Uninstall Istio

[https://istio.io/latest/docs/setup/getting-started/#uninstall](https://istio.io/latest/docs/setup/getting-started/#uninstall)
```
istioctl manifest generate --set profile=demo | kubectl delete -f -
kubectl delete namespace istio-system
```
