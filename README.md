# MANRS Observatory

Observatoire de la sécurité du routage Internet en Afrique de l'Ouest.

## État actuel

**Vous commencez ici.** C'est un template vierge pour reprendre le développement.

### Référence d'apprentissage
Consultez le repo archive pour voir l'implémentation complète :
- https://github.com/aboudou-cto-bloko/manrs-observatory

Dans l'archive :
- `GUIDE_MODULES.md` — Architecture par module (5 modules)
- `TUTORIEL_COMPLET.md` — Pourquoi de chaque décision
- Code source complet (backend, frontend, doc)
- Mémoire de fin d'études

## Avant de commencer

1. **Lire le guide** :
   ```bash
   git clone https://github.com/aboudou-cto-bloko/manrs-observatory.git archive
   cd archive
   cat README.md              # Contexte complet
   cat GUIDE_MODULES.md       # Architecture
   cat TUTORIEL_COMPLET.md    # Pourquoi chaque décision
   ```

2. **Comprendre l'architecture** :
   - Module 1 : Base de données PostgreSQL
   - Module 2 : Collecteur Python (5 APIs)
   - Module 3 : API REST FastAPI
   - Module 4 : Frontend React
   - Module 5 : Déploiement Docker

3. **Comprendre l'objectif** :
   - Mesurer la conformité MANRS de 477 opérateurs réseau
   - 4 actions MANRS : filtering, anti-spoofing, coordination, validation
   - 16 pays d'Afrique de l'Ouest
   - Dashboard interactif avec carte + graphiques

## Étapes de reprise

### Phase 1 : Mise en place de la base
- [ ] Initialiser le projet (structure, git)
- [ ] Créer le schéma PostgreSQL (4 tables)
- [ ] Démarrer docker-compose pour DB

### Phase 2 : Backend
- [ ] Développer le collecteur (5 APIs)
- [ ] Développer l'API FastAPI (5 endpoints)
- [ ] Tests du collecteur et API

### Phase 3 : Frontend
- [ ] Créer l'interface React (Atomic Design)
- [ ] Intégrer les graphiques (Recharts)
- [ ] Intégrer la carte (Leaflet)

### Phase 4 : Déploiement
- [ ] Docker (Dockerfile + docker-compose)
- [ ] Déploiement en ligne
- [ ] Tests en production

### Phase 5 : Finalisations
- [ ] Compléter le mémoire
- [ ] Créer les slides (10 slides)
- [ ] Soutenance

## Équipe

**Contributeurs** :
- François Mawutô Aboudou ZINSOU
- TOUGAN Dodds

**Accompagnateur** : [À remplir]

## Ressources

- **Archive complète** : https://github.com/aboudou-cto-bloko/manrs-observatory
- **Problématique** : Mesurer la conformité MANRS en Afrique de l'Ouest
- **Stack** : Python/FastAPI/React/PostgreSQL/Docker
- **Données** : 477 ASN × 16 pays (6810 préfixes)

## Prochaine étape

1. Cloner l'archive pour voir l'implémentation
2. Lire `GUIDE_MODULES.md` pour comprendre chaque module
3. Créer votre structure de projet
4. Commencer le Module 1 (base de données)

---

**Bonne chance pour la reprise ! 🚀**
