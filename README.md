# 📚 **docker-quotes** - Projet Fullstack avec Node.js, React et Docker

Une application fullstack qui permet d'afficher et d'ajouter des **citations aléatoires** via une **API Express (Node.js)** avec un **frontend React**. Le projet est entièrement conteneurisé avec **Docker** et orchestré avec **Docker Compose** pour simplifier le déploiement et le développement local.

---

## 🚀 **Lancer le projet**

### 1. **Prérequis**

Avant de commencer, assurez-vous d'avoir installé les outils suivants :

- [Docker](https://www.docker.com/) : Plateforme de conteneurisation
- [Docker Compose](https://docs.docker.com/compose/) : Outil pour définir et exécuter des applications multi-conteneurs

### 2. **Cloner le projet**

Si tu n'as pas encore cloné le projet, fais-le avec la commande suivante :

```bash
git clone https://github.com/marcyannick1/docker-quotes.git
cd docker-quotes
```

### 3. **Démarrer les services avec Docker Compose**

Dans le dossier du projet, exécute la commande suivante pour démarrer les conteneurs backend et frontend :

```bash
docker-compose up
```

Cette commande va :
- Télécharger les images Docker depuis Docker Hub.
- Lancer les conteneurs.
- Assurer que le backend est accessible sur http://localhost:4000 et le frontend sur http://localhost:3000.

### 4. **Accéder à l'application**
- Frontend (React) : http://localhost:3000
- Backend (API) : http://localhost:4000/quotes

## 🌐 **Fonctionnalités**

### 1. **Backend (Node.js + Express)**
- GET /quotes : Retourne une citation aléatoire.
- POST /quotes : Permet d'ajouter une nouvelle citation au backend.

### 2. **Frontend (React)**
- Affiche une citation aléatoire récupérée depuis l'API backend.
- Permet à l'utilisateur d'ajouter une nouvelle citation via un formulaire.
- Un bouton "Nouvelle citation" permet de récupérer une citation différente à chaque clic.

## 🏗️ **Structure du projet**

```
docker-quote/
├── docker-compose.yml            # Configuration Docker Compose
└── README.md                     # Documentation principale du projet
```

## 🐳 **Images Docker**

Les images de ce projet sont disponibles sur Docker Hub :

- Backend : `marcyannick/docker-quotes-back`
- Frontend : `marcyannick/docker-quotes-front`

Vous pouvez les utiliser directement dans votre propre environnement avec :

```bash
docker pull marcyannick/docker-quotes-back
docker pull marcyannick/docker-quotes-front
```

## 🔧 **Commandes utiles**

### Docker

```bash
# Démarrer les services en arrière-plan
docker-compose up -d

# Arrêter les services
docker-compose down

# Voir les logs des conteneurs
docker-compose logs -f

# Redémarrer un service spécifique 
docker-compose restart frontend
```


## **🤔 Questions de réflexion**

**1. Quelle différence fais-tu entre un Dockerfile et un docker-compose.yml ?**

•  **Dockerfile** : Fichier pour **construire une image Docker** en définissant les étapes nécessaires (installer dépendances, copier fichiers, configurer l’environnement).

•  **docker-compose.yml** : Fichier pour **orchestrer plusieurs conteneurs Docker**, définir comment ils interagissent (réseaux, volumes, ports).

----------

**2. Quels sont les avantages de séparer les services dans une architecture Docker ?**

•  **Isolation** : Chaque service est indépendant et ne perturbe pas les autres.

•  **Scalabilité** : On peut scaler les services individuellement selon les besoins.

•  **Maintenance simplifiée** : Les services peuvent être redémarrés ou mis à jour sans affecter les autres.

----------

**3. En quoi Docker Compose facilite-t-il le travail en équipe et le déploiement ?**

•  **Facilité de configuration** : Une seule commande (docker-compose up) pour démarrer tous les services, quel que soit l’environnement.

•  **Cohérence** : Les environnements de développement et de production sont identiques.

•  **Collaboration** : Les membres de l’équipe partagent la même configuration de conteneur.

----------

**4. Pourquoi est-il utile de publier une image sur Docker Hub même pour un projet perso ?**

•  **Facilité d’accès** : Permet de partager l’image avec d’autres ou de la récupérer sur différentes machines.

•  **Simplicité de déploiement** : L’image peut être déployée facilement depuis n’importe où.

•  **Réutilisation** : Accès facile à l’image pour des tests ou mises à jour futures.