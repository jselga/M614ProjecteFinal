# ANNEX – Gestió de secrets en entorns professionals

Aquest document complementa el Projecte de Síntesi i explica com es gestionen les credencials i dades sensibles en entorns professionals.

---

# 1. Què és un secret?

En desenvolupament web, un *secret* és qualsevol dada que no pot ser pública perquè compromet la seguretat del sistema.

Exemples habituals:

- Contrasenyes de bases de dades
- Claus privades (JWT, API keys)
- Tokens d’accés a serveis externs
- Claus SSH
- Credencials de passarel·les de pagament (Stripe, PayPal, etc.)

Si un secret es publica en un repositori públic, es considera compromès i s’ha de regenerar immediatament.

---

# 2. Per què no es versionen els secrets?

Els repositoris Git:

- Guarden historial complet
- Poden ser clonats indefinidament
- Poden ser públics o compartits

Encara que s’esborri un secret en un commit posterior, pot continuar existint en l’historial.

Per aquest motiu:

> Els secrets mai s’han d’incloure en fitxers versionats.

---

# 3. Gestió en entorn de desenvolupament

En equips professionals, el procediment habitual és:

1. Incloure un fitxer `.env.example` al repositori.
2. Cada desenvolupador crea el seu propi `.env` local.
3. El fitxer `.env` està inclòs al `.gitignore`.

Exemple:

```
cp .env.example .env
```

El `.env.example` només conté variables necessàries, però no secrets reals.

---

# 4. Gestió en entorn Docker

En entorns professionals amb Docker:

- Les variables sensibles es defineixen fora del repositori.
- Es poden injectar mitjançant variables d’entorn del sistema.
- Es poden utilitzar fitxers externs no versionats.

En entorns més avançats es poden utilitzar:

- Docker Secrets
- Gestors de secrets (Vault, AWS Secrets Manager, etc.)

---

# 5. Gestió en producció

En producció, les credencials:

- Es configuren al servidor o plataforma de desplegament.
- No apareixen al codi font.
- No es documenten públicament.

Plataformes com AWS, Azure o DigitalOcean permeten definir variables d’entorn des del panell de control.

---

# 6. Diferència entre entorn acadèmic i professional

En aquest projecte acadèmic:

- Les credencials són de desenvolupament.
- No tenen valor real.
- Poden aparèixer en `docker-compose.yml` si és necessari per facilitar l’execució.

En un entorn professional real:

- Les credencials mai estarien al repositori.
- S’utilitzarien mecanismes segurs d’injecció de secrets.

---

# 7. Bones pràctiques bàsiques

- No pujar mai el fitxer `.env`.
- Revisar sempre el `.gitignore`.
- No escriure claus reals al README.
- Entendre la diferència entre configuració i secret.

---

# Conclusió

La gestió correcta de secrets és una responsabilitat professional.

Un projecte no és només funcional quan funciona, sinó quan és segur, mantenible i desplegable sense comprometre dades sensibles.

