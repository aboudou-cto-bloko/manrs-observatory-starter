# MANRS Observatory

Observatoire de la sécurité du routage Internet en Afrique de l'Ouest.

## État actuel (Juin 2026)

### ✅ Complété
- [x] Base de données PostgreSQL (4 tables)
- [x] Collecteur Python (477 ASN × 6810 préfixes collectés)
- [x] API REST FastAPI (5 endpoints)
- [x] Frontend React (5 pages)
- [x] Docker Compose (infrastructure complète)
- [x] Mémoire de fin d'études (36 pages)
- [x] Documentation technique (guides + tutoriel)

### 📊 Résultats de la première collecte (24 juin 2026)
- **477 ASN** surveillés dans 16 pays
- **11 membres MANRS** (2.3%)
- **51.4%** couverture ROA globale
- **0%** anti-spoofing (aucun ASN testé bloque le spoofing)
- **Top** : Mali 60% ROA, Burkina 57.7%
- **Bottom** : Mauritanie 0%, Guinée-Bissau 0%

## À faire (Priorités)

### 🔴 Priorité 1 — Déploiement bloquant
- [ ] Créer `frontend/Dockerfile` (multi-stage : build + nginx)
- [ ] Créer `README.md` racine (CDC : lancer en 10 min max)
- [ ] Tester `docker compose up` complet end-to-end

### 🟠 Priorité 2 — Mise en ligne
- [ ] Déployer backend (Render.com free tier ou Railway)
- [ ] Déployer frontend (Vercel)
- [ ] URL de démo en ligne (pour présentation)

### 🟡 Priorité 3 — Mémoire + présentation
- [ ] Remplir placeholders `[À compléter]` dans main.tex (page de garde, chapitre stage)
- [ ] Créer 10 slides de soutenance (contexte, problématique, architecture, démo, résultats, recommandations)

## Démarrage rapide

```bash
# Cloner l'archive complète (référence)
git clone https://github.com/aboudou-cto-bloko/manrs-observatory.git archive

# Consulter les guides (dans l'archive)
cd archive
cat GUIDE_MODULES.md          # Par module
cat TUTORIEL_COMPLET.md       # Pédagogique
cat main.pdf                  # Mémoire

# Lancer le projet
docker compose up -d
# Frontend : http://localhost:3000
# API docs : http://localhost:8000/docs
```

## Points critiques à connaître

### 🗄️ Base de données
- 4 tables : `asn`, `prefixes`, `countries`, `ai_recommendations`
- UPSERT pattern : pas de doublons si re-collecte
- LATERAL JOIN pour ROA coverage % (calculé à la volée)

### 🔄 Collecteur
- 5 sources APIs : MANRS v2 + RIPE Stat + RPKI Validator + PeeringDB + CAIDA Spoofer
- Rate limit 0.5s entre requêtes (respect des APIs)
- Scheduling 6h automatique (met à jour le dashboard)
- Try/except par ASN : si un échoue, le collecteur continue

### 🌐 API
- FastAPI + RealDictCursor (JSON direct, pas de DTO)
- CORS pour localhost:3000
- 5 endpoints : stats, countries, countries/{code}, asn/{number}, search

### ⚛️ Frontend
- React 19 + TypeScript strict (pas de `any`)
- Atomic Design : atoms → molecules → organisms → pages
- Phosphor Icons (remplace emojis)
- Recharts (graphiques) + Leaflet (carte interactive)
- Dark theme avec filter CSS sur Leaflet

## Équipe

- **Développeur principal** : François Mawutô Aboudou ZINSOU
- **Binôme** : dodds6304
- **Accompagnateur** : [À remplir par l'accompagnateur]

## Liens utiles

- **Archive complète** : https://github.com/aboudou-cto-bloko/manrs-observatory
- **Mémoire** : `main.pdf` (dans l'archive)
- **API MANRS** : https://observatory.manrs.org
- **RPKI Validator** : https://rpki-validator.ripe.net
- **PeeringDB** : https://www.peeringdb.com
