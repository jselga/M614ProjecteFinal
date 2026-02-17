# PROJECTE DE SÍNTESI
## Mòdul 614: Desplegament d’Aplicacions Web (DAW)
### Títol: *Del projecte funcional al desplegament professional*

**Durada aproximada:** 12 hores   
**Modalitat:** grups de dues persones  
**Lliurament:** Repositori Git + documentació + demostració final

---

# 1. Context

En aquest projecte recuperareu una aplicació web desenvolupada en un altre mòdul (Entorn Client o Entorn Servidor).

Pot ser:

- Una aplicació basada en **Laravel**
- Una aplicació basada en **React**
- Un projecte fullstack senzill

L’objectiu NO és desenvolupar funcionalitat nova complexa.  
L’objectiu és convertir aquest projecte en:

- Un repositori col·laboratiu ben gestionat amb Git
- Un projecte amb conflictes reals resolts correctament
- Una aplicació dockeritzada i executable amb una única comanda
- Un projecte documentat professionalment

---

# 2. Objectius d’aprenentatge

En acabar el projecte haureu de demostrar que sabeu:

- Aplicar un **workflow real amb Git** (branques, merges, etiquetes)
- Provocar i resoldre **conflictes reals de manera argumentada**
- Dockeritzar una aplicació web (Laravel o React)
- Utilitzar variables d’entorn correctament
- Documentar processos tècnics
- Fer una entrega reproduïble

---

# 3. Requisits del projecte

## A) Control de versions (Git)

El repositori ha d’incloure:

- `.gitignore` correcte
- Missatges de commit descriptius
- Ús de branques (`feature/...`, `fix/...`)
- Mínim **2 Pull Requests o merges documentats**

---

## B) Conflictes obligatoris

S’han de provocar i resoldre **mínim 2 conflictes diferents**.

### Conflicte 1 — Mateixa línia (textual)

- Cada alumne modifica el mateix fragment d’un fitxer (component React, vista Blade, controlador, etc.).
- Es genera conflicte en fer merge.
- Es resol manualment.
- Es documenta el procés.

---

### Conflicte 2 — Dependències o estructura

Opcions vàlides:

- Conflicte en `composer.json`
- Conflicte en `package.json`
- Rename/move d’un fitxer mentre l’altre l’edita

Ha de quedar evidència real del conflicte.

---

### Documentació obligatòria del conflicte

Per cada conflicte cal explicar:

- Com s’ha provocat
- Quin missatge d’error ha aparegut
- Quins marcadors de conflicte han sortit (`<<<<<<<`)
- Com s’ha resolt
- Per què s’ha triat aquesta solució


---

## C) Dockerització

El projecte ha de poder executar-se amb:

```
docker compose up --build
```

Segons el tipus de projecte:

### Si és Laravel:

- Dockerfile per a l’aplicació
- Servei base de dades (MySQL o similar)
- Variables via `.env.example`
- Volum per persistència

### Si és React:

- Multi-stage build (Dockerfile amb etapa build i etapa servidor)
- Servidor Nginx per servir el build
- docker-compose (mínim un servei)

---

### Requisits obligatoris:

- No es poden versionar secrets
- Les variables d’entorn han d’estar documentades
- Ports correctament exposats/publicats
- El projecte ha de funcionar des de zero en un altre ordinador  
  
[Veure Annex gestió de secrets](./annex-gestio-secrets.md)

---

## D) Documentació

El repositori ha d’incloure:

### README.md

Ha d’explicar:

- Descripció del projecte
- Arquitectura
- Requisits
- Execució local
- Execució amb Docker
- Troubleshooting bàsic

---

### REPORT.md

Ha d’incloure:

- Estat inicial del projecte
- Workflow Git aplicat
- Explicació detallada dels conflictes
- Problemes trobats
- Decisions tècniques
- Repartiment de tasques
- Temps invertit  
[Veure model de REPORT](./REPORT.md)

---


# 4. Defensa final

Cada parella haurà de fer una demostració de 3–5 minuts on mostri:

- Un conflicte real al repositori
- La resolució aplicada
- L’execució amb Docker
- Organització del grup per resoldre el projecte

---

# 5. Normes importants

- No es pot reutilitzar exactament el projecte sense millores estructurals.
- No es poden eliminar conflictes sense documentar-los.
- No es pot modificar directament `main` sense branques.

# 6. AMPLIACIÓ 
## Desplegament al núvol i CI/CD

Aquesta ampliació està pensada per a equips que hagin completat correctament el projecte base (Git + conflictes + Docker).

### 1. Integració Contínua (CI)

Cal configurar un workflow de GitHub Actions que:

- S’executi en cada `push` a `main`.
- Instal·li les dependències del projecte.
- Executi el build de producció (`npm run build`, `composer install` o equivalent).
- Verifiqui que la imatge Docker es construeix correctament (`docker build`).

Requisits mínims:

- Fitxer `.github/workflows/ci.yml` versionat.
- Pipeline executant-se correctament (evidència amb captura o enllaç).

### 2. Desplegament Continu (CD bàsic)

Opcions vàlides:

- Desplegament del frontend React a Vercel o Netlify.
- Desplegament a Render o Railway.
- Desplegament en un servidor amb Docker instal·lat.

Requisits mínims:

- Configurar correctament les variables d’entorn al panell del proveïdor.
- Documentar els passos realitzats.
- Incloure l’enllaç públic a l’aplicació desplegada.

Aquesta ampliació pot servir per obtenir qualificació d’excel·lència.


---

## Competència professional treballada

Aquest projecte simula una situació real:

> Rebre un projecte funcional però no desplegable i convertir-lo en un projecte professional, versionat i reproduïble.

