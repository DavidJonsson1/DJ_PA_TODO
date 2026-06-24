# DJ PA Migration Tasks

## Dev

| Status      | Task                                       | Comment                                                       |
| ----------- | ------------------------------------------ | ------------------------------------------------------------- |
| Done | Configure Azure OIDC for K8s               | Validate workload identity authentication                     |
| Done | Configure Azure OIDC for ArgoCD            | Depends on K8s OIDC                                           |
| Done | Validate ArgoCD SSO login                  | Verify Azure OIDC authentication works                        |
| Not Started | Configure Grafana OIDC | ProAct to configure Grafana login using Azure OIDC |
| Not Started | Validate Grafana SSO login | Verify users can sign in and have correct permissions |
| Not Started | Create public DNS records                  | Add A/CNAME records for required hostnames; or can we make it without (fejk hosts file) |
| Not Started | Konfigurera DNS-01 solver i ClusterIssuer mot Azure DNS	NP (Proact managed) | Will this work?! | 
| Not Started | Sätt upp wildcard-listener *.fridaqa.nordicport.se i shared-gateway | Will this work with a local hosts file edit? |  
| Done | Configure Ivanti VPN whitelist for K8s     | Verify approved VPN source IPs                                |
| In Progress | Configure Ivanti VPN whitelist for ArgoCD  | Verify approved VPN source IPs                                |
| In Progress | Configure routing and whitelist K8s → SQL  | Requires network approval                                     |
| Not Started | Deploy Gateway API resources               | Replace NGINX ingress controller                              |
| Not Started | Migrate ingress definitions to Gateway API | Verify all routes are migrated                                |
| Not Started | Configure Gateway TLS per hostname         | Create certificate references for each hostname               |
| Not Started | Migrate cert-manager certificate handling  | Replace Ingress TLS annotations with Gateway-compatible setup |
| Not Started | Verify certificate issuance per hostname   | Validate certificates for all exposed hostnames               |
| Not Started | Verify certificate renewal                 | Confirm automatic renewal works after Gateway migration       |
| Not Started | Validate VPN-only access                   | Access works through Ivanti VPN and is blocked publicly       |
| Not Started | Validate application routing               | Verify all services are reachable                             |
| Not Started | Validate SQL connectivity                  | Verify applications can access SQL endpoints                  |
| Not Started | Validate ArgoCD sync and deployments       | Verify GitOps workflows function correctly                    |
| Not Started | Dev sign-off                               | All validation completed                                      |

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
