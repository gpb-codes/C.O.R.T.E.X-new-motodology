# MOC -- Ciberseguridad

## Proposito

Mapa de conocimiento sobre seguridad informatica: proteccion de sistemas, redes, aplicaciones y datos.

---

## Arbol de conocimiento

```
Ciberseguridad
├── OWASP Top 10
│   ├── Injection (SQL, NoSQL, OS)
│   ├── Broken Authentication
│   ├── Sensitive Data Exposure
│   ├── XXE / XSS / CSRF
│   └── Insecure Deserialization
├── Seguridad en APIs
│   ├── Rate limiting
│   ├── JWT / OAuth 2.0 / OpenID Connect
│   ├── API keys management
│   └── Input validation
├── Autenticacion y autorizacion
│   ├── RBAC / ABAC
│   ├── MFA / 2FA
│   └── Session management
├── Criptografia
│   ├── Simetrica (AES) vs Asimetrica (RSA, ECC)
│   ├── Hashing (SHA, bcrypt, argon2)
│   └── TLS / SSL
├── Network security
│   ├── Firewalls / WAF
│   ├── VPN / Zero Trust
│   └── IDS / IPS
├── Secure coding
│   ├── Input sanitization
│   ├── Output encoding
│   └── Principle of least privilege
└── Pentesting
    ├── Reconocimiento
    ├── Escaneo
    ├── Explotacion
    └── Post-explotacion
```

## Notas relacionadas

```dataview
TABLE
  file.mtime as "Ultima modificacion"
FROM #conocimiento/ciberseguridad
SORT file.mtime DESC
```

## Recursos externos

| Recurso | Tipo | Link |
|---|---|---|
| OWASP | Web | https://owasp.org |
|  |  |  |

## Pendientes

- [ ] 
