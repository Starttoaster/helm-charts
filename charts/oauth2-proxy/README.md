# oauth2-proxy

This is my helm chart for [oauth2-proxy](https://github.com/oauth2-proxy/oauth2-proxy).

## Example Installation

```yaml
config:
  issuerURL: "https://identityprovider.example.com"
  redirectURL: "https://app.example.com/oauth2/callback"
  upstream: "http://app-name.app-namespace.svc.cluster.local:8080"

secret:
  clientId: $CLIENT_ID
  clientSecret: $CLIENT_SECRET
  cookieSecret: $COOKIE_SECRET

gatewayAPI:
  httpRoute:
    enabled: true
    parentRefs:
      - group: gateway.networking.k8s.io
        kind: Gateway
        name: default-internal
        namespace: gateway-system
    hostnames:
      - app.example.com
```