# ZAP by Checkmarx Scanning Report - Round 1

**Generated with ZAP on Sun 14 Dec 2025, at 13:52:22**
**ZAP Version:** 2.16.1

---

## 📋 Yhteenveto (Summaries)

### Varoitusten Määrät Riskin ja Luottamuksen Mukaan

| Riski | User Confirmed | High | Medium | Low | **Total** |
| :--- | :--- | :--- | :--- | :--- | :--- |
| High | 0 | 0 | 0 | 0 | **0** |
| **Medium** | 0 | 0 | 0 | **1** | **1** |
| Low | 0 | 0 | 0 | 0 | **0** |
| **Informational** | 0 | 0 | **1** | 0 | **1** |
| **Total** | **0** | **0** | **1** | **1** | **2** |

### Varoitukset Sivuston ja Riskin Mukaan

| Riski | High | Medium | Informational |
| :--- | :--- | :--- |
| **http://localhost:8001** | 0 | **1** | **1** |

---

## 🚨 Varoitukset (Alerts)

### 1. Absence of Anti-CSRF Tokens (CSRF-tunnusten puuttuminen)

| Ominaisuus | Arvo |
| :--- | :--- |
| **Riski** | **Medium (Keskisuuri)** |
| **Luottamus** | Low (Matala) |
| **URL** | `GET http://localhost:8001/register` |
| **Tagit** | OWASP\_2021\_A01, CWE-352 |

#### Kuvaus

HTML-lähetyslomakkeesta ei löytynyt Anti-CSRF-tunnuksia. Rekisteröintilomake on altis Cross-Site Request Forgery (CSRF) -hyökkäykselle, jossa hyökkääjä voi pakottaa uhrin (jolla on aktiivinen istunto) suorittamaan pyynnön ilman hänen tietoaan (esim. luomaan uuden käyttäjän).

#### Todiste (Evidence)

```html
<form action="/register" method="POST">
