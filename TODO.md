# DJ PA Migration Tasks

## Dev

| Status      | Task                                       | Comment                                                       |
| ----------- | ------------------------------------------ | ------------------------------------------------------------- |
| Done | Configure Azure OIDC for K8s               | Validate workload identity authentication                     |
| Done | Configure Azure OIDC for ArgoCD            | Depends on K8s OIDC                                           |
| Done | Validate ArgoCD SSO login                  | Verify Azure OIDC authentication works                        |
| Not Started | Configure Grafana OIDC | ProAct to configure Grafana login using Azure OIDC |
| Not Started | Validate Grafana SSO login | Verify users can sign in and have correct permissions |
| Blocked | Configure DNS-01 solver in ClusterIssuer against Azure DNS | Proact task. Requires DNS Zone Contributor on fridaqa.nordicport.se in Azure DNS |
| Blocked | Set up wildcard listener *.fridaqa.nordicport.se in shared-gateway | Proact task. Local hosts file testing works independently |
| Done | Configure Ivanti VPN whitelist for K8s     | Verify approved VPN source IPs                                |
| In Progress | Configure Ivanti VPN whitelist for ArgoCD  | Verify approved VPN source IPs                                |
| In Progress | Configure routing and whitelist K8s → SQL  | Requires network approval                                     |
| Done | Deploy Gateway API resources               | shared-gateway running in namespace gateway (Proact-managed)  |
| Not Started | Migrate ingress definitions to Gateway API | Replace Ingress with HTTPRoute in services/ and platform/. See GATEWAY-MIGRATION.md |
| Blocked | Configure Gateway TLS per hostname         | Awaiting wildcard listener + DNS-01 solver from Proact        |
| Blocked | Migrate cert-manager certificate handling  | Certs managed centrally by Proact. Awaiting DNS-01 + wildcard |
| Blocked | Verify certificate issuance per hostname   | Awaiting Proact (DNS-01 solver + wildcard listener)           |
| Blocked | Verify certificate renewal                 | Awaiting Proact (DNS-01 solver + wildcard listener)           |
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
