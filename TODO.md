# DJ PA Migration Tasks

## Dev

| Status      | Task                                       | Comment                                                 |
| ----------- | ------------------------------------------ | ------------------------------------------------------- |
| Not Started | Configure Azure OIDC for K8s               | Validate workload identity authentication               |
| Not Started | Configure Azure OIDC for ArgoCD            | Depends on K8s OIDC                                     |
| Not Started | Validate ArgoCD SSO login                  | Verify Azure OIDC authentication works                  |
| Not Started | Create wildcard DNS A-record               | `*.dev02.nordicport.se` → Public LoadBalancer IP        |
| Not Started | Configure Ivanti VPN whitelist for K8s     | Verify approved VPN source IPs                          |
| Not Started | Configure Ivanti VPN whitelist for ArgoCD  | Verify approved VPN source IPs                          |
| Not Started | Configure routing and whitelist K8s → SQL  | Requires network approval                               |
| Not Started | Deploy Gateway API resources               | Replace NGINX ingress controller                        |
| Not Started | Migrate ingress definitions to Gateway API | Verify all routes are migrated                          |
| Not Started | Configure Gateway TLS                      | Use `cert-manager.io/cluster-issuer: letsencrypt-prod`  |
| Not Started | Verify certificate issuance                | Confirm certificate is generated successfully           |
| Not Started | Verify certificate renewal                 | Confirm automatic renewal works                         |
| Not Started | Validate VPN-only access                   | Access works through Ivanti VPN and is blocked publicly |
| Not Started | Validate application routing               | Verify all services are reachable                       |
| Not Started | Validate SQL connectivity                  | Verify applications can access SQL endpoints            |
| Not Started | Validate ArgoCD sync and deployments       | Verify GitOps workflows function correctly              |
| Not Started | Dev sign-off                               | All validation completed                                |

---

## Prod

> Start after successful Dev validation and sign-off.

| Status      | Task                                       | Comment                                                 |
| ----------- | ------------------------------------------ | ------------------------------------------------------- |
| Blocked | Start Prod rollout | Awaiting successful Dev validation |

---

## Status Values

* Not Started
* In Progress
* Blocked
* Done
