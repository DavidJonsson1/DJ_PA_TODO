# Infrastructure Tasks

## Dev

| Status      | Task                          | Comment                        |
| ----------- | ----------------------------- | ------------------------------ |
| Done        | Azure OIDC for K8s            |                                |
| Done        | Azure OIDC for ArgoCD         | Depends on K8s OIDC            |
| Done        | Whitelist Ivanti VPN K8s      | Confirm source IP ranges       |
| In Progress | Whitelist Ivanti VPN ArgoCD   | Confirm source IP ranges       |
| Not Started | Routing + Whitelist K8s → SQL | Requires network team approval |
| Not Started | Create wildcard DNS A-record | `*.dev02.nordicport.se` → Public LoadBalancer IP |
| Not Started | Configure ingress/network whitelist | Allow Ivanti VPN egress IPs only |
| Not Started | Validate access restrictions | Access works via VPN, blocked from public internet |
| Not Started | Configure Gateway TLS certificate generation | Use `cert-manager.io/cluster-issuer: letsencrypt-prod` on Gateway |
| Not Started | Verify DNS-01 challenge for wildcard cert | Required for `*.dev02.nordicport.se` |
| Not Started | Validate TLS renewal with Gateway API | Confirm cert-manager renews cert after nginx → Gateway migration |

## Prod

> Start after successful validation in Dev.

| Status      | Task                          | Comment                        |
| ----------- | ----------------------------- | ------------------------------ |
| Not Started | Azure OIDC for K8s            |                                |
| Not Started | Azure OIDC for ArgoCD         | Depends on K8s OIDC            |
| Not Started | Whitelist Ivanti VPN K8s      | Confirm source IP ranges       |
| Not Started | Whitelist Ivanti VPN ArgoCD   | Confirm source IP ranges       |
| Not Started | Routing + Whitelist K8s → SQL | Requires network team approval |
| WIP | WIP | WIP |


## Legend

* Not Started
* In Progress
* Done
