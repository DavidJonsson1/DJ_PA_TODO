# DJ PA Migration Tasks

## Dev

| Status      | Task                                       | Who         | Comment                                                       |
| ----------- | ------------------------------------------ | ----------- | ------------------------------------------------------------- |
| ✅ Done | Configure Azure OIDC for K8s               | Both  | Validate workload identity authentication                     |
| ✅ Done | Configure Azure OIDC for ArgoCD            | Both  | Depends on K8s OIDC                                           |
| ✅ Done | Validate ArgoCD SSO login                  | NordicPort  | Verify Azure OIDC authentication works                        |
| ✅ Done | Configure Ivanti VPN whitelist for K8s     | Proact        | Verify approved VPN source IPs                                |
| ✅ Done | Configure routing and whitelist K8s → SQL  | Proact        | Requires network approval                                     |
| ✅ Done | Validate SQL connectivity                  | NordicPort  | Verify applications can access SQL endpoints                  |
| ✅ Done | Configure Ivanti VPN whitelist for ArgoCD | Proact   | Verify approved VPN source IPs                                |
| 🔄 In Progress | Configure Grafana OIDC                | Both      | ProAct to configure Grafana login using Azure OIDC |
| ⛔ Blocked | Configure DNS-01 solver in ClusterIssuer  | Proact      | Proact task. Needs DNS Zone Contributor on Azure DNS zone     |
| ⛔ Blocked | Set up wildcard listener *.fridaqa.nordicport.se | Proact | Proact task. Blocked by DNS-01 solver above              |
| ⛔ Blocked | Configure Gateway TLS per hostname         | Both      | DJ needs help. Awaiting wildcard listener + DNS-01 solver from Proact        |
| ⛔ Blocked | Migrate cert-manager certificate handling  | Both      | DJ needs help. Certs managed centrally by Proact. Awaiting DNS-01 + wildcard |
| ⛔ Blocked | Verify certificate issuance per hostname   | Both        | Awaiting Proact (DNS-01 solver + wildcard listener)           |
| ⛔ Blocked | Verify certificate renewal                 | Both        | Awaiting Proact (DNS-01 solver + wildcard listener)           |
| ⬜ Not Started | Validate Grafana SSO login            | NordicPort  | Verify users can sign in and have correct permissions |
| ⬜ Not Started | Migrate ingress definitions to Gateway API | NordicPort | Replace Ingress with HTTPRoute in services/ and platform/. See GATEWAY-MIGRATION.md |
| ⬜ Not Started | Validate VPN-only access               | NordicPort  | Access works through Ivanti VPN and is blocked publicly       |
| ⬜ Not Started | Validate application routing           | NordicPort  | Verify all services are reachable                             |
| ⬜ Not Started | Validate ArgoCD sync and deployments   | NordicPort  | Verify GitOps workflows function correctly                    |
| ⬜ Not Started | Dev sign-off                           | Both        | All validation completed                                      |

---

## Prod

> Start after successful Dev validation and sign-off.

| Status      | Task                                       | Who         | Comment                                                 |
| ----------- | ------------------------------------------ | ----------- | ------------------------------------------------------- |
| ⛔ Blocked | Start Prod rollout                          | Both        | Awaiting successful Dev validation |

---

## Status Values

* ✅ Done
* 🔄 In Progress
* ⛔ Blocked
* ⬜ Not Started
