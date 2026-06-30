# MANRS Observatory — Reprise de développement

État : Juin 2026  
Binôme : [Ajouter noms]  
Dernière mise à jour : [Ajouter date]

## Objectif

Observatoire de la sécurité du routage Internet en Afrique de l'Ouest.  
Mesure la conformité de 477 opérateurs réseau aux 4 actions MANRS.

## État du projet

### ✅ Fait
- Base de données PostgreSQL (4 tables)
- Collecteur Python (5 sources, scheduling 6h)
- API FastAPI (5 endpoints)
- Frontend React (5 pages, Atomic Design)
- Docker Compose (infrastructure conteneurisée)
- Mémoire LaTeX (36 pages, figures)

### ⚠️ À faire
- Dockerfile frontend (multi-stage)
- README.md racine
- Déploiement (Render/Vercel)
- Slides soutenance (10 slides)
- Placeholders mémoire LaTeX

## Démarrage rapide

### 1. Lancer le projet localement

```bash
# Clone
git clone https://github.com/aboudou-cto-bloko/manrs-observatory.git
cd manrs-observatory

# Démarrer les conteneurs
docker compose up -d

# Vérifier que tout tourne
docker compose ps

# URLs
- Frontend : http://localhost:3000
- API : http://localhost:8000/docs
- PostgreSQL : localhost:5432
```

### 2. Consulter la documentation

| Fichier | Contenu |
|---------|---------|
| `GUIDE_MODULES.md` | Guide par module (5 modules indépendants) |
| `TUTORIEL_COMPLET.md` | Tutoriel pédagogique (pourquoi/comment/flux) |
| `JOURNAL_DEV.md` | Journal de développement |
| `main.pdf` | Mémoire complet (36 pages) |

## Structure du projet

```
manrs-observatory/
├── backend/
│   ├── collector/      # Collecteur Python (5 sources)
│   ├── api/            # API FastAPI
│   ├── db/             # Schéma PostgreSQL
│   ├── Dockerfile      # Image backend
│   └── requirements.txt
├── frontend/
│   ├── src/
│   │   ├── components/ # Atomic Design
│   │   ├── pages/      # 5 pages
│   │   └── lib/        # Client API
│   ├── package.json
│   └── Dockerfile      # À créer
├── docker-compose.yml  # Orche**stration
├── GUIDE_MODULES.md    # Par module
├── TUTORIEL_COMPLET.md # Pédagogique
├── main.pdf            # Mémoire
└── README.md           # Ce fichier
```

## Points critiques à connaître

### Bases de données
- 4 tables : `asn`, `prefixes`, `countries`, `ai_recommendations`
- UPSERT pattern (pas de doublons si re-collecte)
- LATERAL JOIN pour calculer ROA coverage %

### Collecteur
- 5 sources APIs publiques
- Rate limit 0.5s entre requêtes
- Scheduling 6h automatique
- Try/except par ASN (résilience)

### API
- FastAPI + RealDictCursor (sérialisation JSON direct)
- CORS configuré pour localhost:3000
- 5 endpoints : /stats, /countries, /countries/{code}, /asn/{number}, /search

### Frontend
- React 19 + TypeScript strict
- Atomic Design : atoms → molecules → organisms → pages
- Phosphor Icons (remplace emojis)
- Recharts (graphiques) + Leaflet (carte)

## Priorités de continuation

### Priorité 1 (bloquante)
- [ ] Créer `frontend/Dockerfile` (multi-stage)
- [ ] Créer `README.md` racine (CDC exige : lancer en 10 min)
- [ ] Tester `docker compose up` complet

### Priorité 2 (déploiement)
- [ ] Déployer backend sur Render.com (free tier)
- [ ] Déployer frontend sur Vercel
- [ ] Obtenir URL de démo en ligne

### Priorité 3 (mémoire)
- [ ] Remplir les placeholders `[À compléter]` (page de garde + chapitre stage)
- [ ] Créer 10 slides de soutenance

## Contacts et ressources

### Clé API MANRS
- Email : franckzinsou06@gmail.com
- Mot de passe : ManrsObs2026!
- **Expire tous les 3 jours** → voir GUIDE_MODULES.md pour renouvellement

### Observatoire existant
- URL : https://observatory.manrs.org
- Documentation : voir TUTORIEL_COMPLET.md chapitre 3

## Prochaines étapes (après déploiement)

- Module IA : générer recommandations personnalisées par ASN
- Code splitting : passer bundle JS de 847KB à <500KB
- Tests : suite complète (unit + integration)
- CI/CD : GitHub Actions pour tests + déploiement

---

**Comment utiliser ce repo ?**

1. Lire `GUIDE_MODULES.md` pour comprendre l'architecture par module
2. Lire `TUTORIEL_COMPLET.md` pour le "pourquoi" de chaque décision
3. Lancer `docker compose up` et essayer le dashboard
4. Attaquer la priorité 1 de continuation

Bonne reprise ! 🚀
