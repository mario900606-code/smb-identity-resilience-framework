# SMB Identity & Resilience Framework

## Översikt

SMB Identity & Resilience Framework är ett praktiskt cybersäkerhetsprojekt med fokus på identitets- och åtkomsthantering (IAM), Single Sign-On (SSO), multifaktorautentisering (MFA) och cyberresiliens för små och medelstora företag (SMB).

Projektets syfte är att utforska hur mindre organisationer kan implementera centraliserad identitetshantering och modern autentisering med hjälp av open source-teknologier och containeriserad infrastruktur.

---

# Mål

Projektet syftar till att demonstrera:

* Centraliserad identitetshantering (IAM)
* Single Sign-On (SSO)
* Rollbaserad åtkomstkontroll (RBAC)
* Gruppbaserad behörighetsstyrning
* Multifaktorautentisering (MFA)
* Centraliserad administration av användare och behörigheter
* Grundläggande processer för identitetslivscykel och cyberresiliens

---

# Arkitektur

```text
Users
   │
   ▼
Keycloak
(IAM + SSO + MFA)
   │
   │ OpenID Connect (OIDC)
   ▼
Grafana
(Role-Based Access Control)
```

---

# Komponenter

## Keycloak

Keycloak fungerar som central Identity Provider (IdP) och ansvarar för:

* Autentisering
* Användarhantering
* Grupphantering
* Rollhantering
* MFA/TOTP
* Single Sign-On

## Grafana

Grafana används som exempelapplikation för att demonstrera:

* Federerad inloggning
* Rollbaserad åtkomstkontroll
* Automatisk provisionering av användare
* Integration via OpenID Connect

## Docker

Samtliga tjänster körs i containrar för att skapa en portabel och reproducerbar miljö.

---

# Implementerade funktioner

## IAM

* Centraliserad användarhantering
* Realm Roles
* Grupphantering

## SSO

* OpenID Connect (OIDC)
* Federerad autentisering mellan Keycloak och Grafana

## RBAC

Följande roller har implementerats:

* admin
* analyst
* viewer

## Grupper

Följande grupper används:

* IT
* SOC
* Users

Roller tilldelas grupper istället för individuella användare.

## MFA

TOTP-baserad multifaktorautentisering har implementerats med Authenticator-app.

---

# Behörighetsmodell

| Grupp | Roll    | Grafana |
| ----- | ------- | ------- |
| IT    | admin   | Admin   |
| SOC   | analyst | Editor  |
| Users | viewer  | Viewer  |

---

# Exempelorganisation

| Användare | Grupp |
| --------- | ----- |
| Mario     | IT    |
| Elsa      | SOC   |
| Rasmus    | SOC   |
| Martina   | Users |
| Said      | Users |

---

# Onboarding

1. Skapa användare i Keycloak
2. Tilldela lösenord
3. Lägg användaren i rätt grupp
4. Aktivera MFA
5. Användaren får automatiskt rätt åtkomst

---

# Offboarding

1. Inaktivera användaren i Keycloak
2. Återkalla aktiva sessioner
3. Ta bort gruppmedlemskap vid behov
4. Verifiera att åtkomst till anslutna system upphör

---

# Framtida utveckling

Planerade områden för vidare utveckling:

* Identity Governance-koncept
* Access Reviews
* Onboarding- och Offboarding-flöden
* Audit Logging
* Säkerhetsövervakning
* Ytterligare OIDC-integrerade applikationer
* Cyberresiliens och återställningsprocesser

---

# Syfte

Projektet är framtaget som ett praktiskt lärandeprojekt inom cybersäkerhet med fokus på moderna IAM-principer, identitetssäkerhet och operativ resiliens i SMB-miljöer.
