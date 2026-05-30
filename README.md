# SMB Identity & Resilience Framework

Ett praktiskt cybersäkerhetsprojekt med fokus på Identity & Access Management (IAM), Single Sign-On (SSO), Multi-Factor Authentication (MFA) och cyberresiliens för små och medelstora företag (SMB).

## Syfte

Projektet utforskar hur en organisation kan centralisera identitetshantering, autentisering och behörighetsstyrning med hjälp av moderna IAM-principer och open source-teknologier.

## Funktioner

* Centraliserad identitetshantering med Keycloak
* Single Sign-On (SSO)
* OpenID Connect (OIDC)
* Multi-Factor Authentication (MFA)
* Gruppbaserad Role-Based Access Control (RBAC)
* Automatisk användarprovisionering till Grafana
* Containeriserad miljö med Docker

## Arkitektur

```text
Users
   │
   ▼
Keycloak
(IAM + SSO + MFA)
   │
   │ OIDC
   ▼
Grafana
(RBAC)
```

## Implementerade roller

| Grupp | Roll    | Grafana |
| ----- | ------- | ------- |
| IT    | admin   | Admin   |
| SOC   | analyst | Editor  |
| Users | viewer  | Viewer  |

## Teknologier

* Keycloak
* Grafana
* Docker
* OpenID Connect (OIDC)

## Dokumentation

Mer detaljerad dokumentation finns under:

* docs/architecture.md

## Status

Aktuellt fokus:

* IAM
* SSO
* MFA
* Gruppbaserad RBAC
* Identity Lifecycle Management

## Framtida utveckling

* Onboarding- och offboardingprocesser
* Access Reviews
* Audit Logging
* Identity Governance-koncept
* Fler OIDC-integrerade applikationer
* Förbättrad cyberresiliens
