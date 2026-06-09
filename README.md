# Esprit Market

## Nom du projet
**Esprit Market** - Plateforme E-commerce Intelligente avec IA

## Description
**Esprit Market** est une plateforme e-commerce complète et intelligente développée dans le cadre du PIDEV (Projet Intégré de Développement) en 4ème année d'Ingénierie à **l'École Supérieure Privée d'Ingénierie et de Technologies (ESPRIT) – Tunisie**.

Cette marketplace moderne offre une solution robuste avec des fonctionnalités avancées d'intelligence artificielle pour les utilisateurs, vendeurs et administrateurs, permettant de gérer les produits, commandes et transactions de manière intelligente et automatisée.

Le projet a été développé durant l'**année académique 2025–2026** et démontre l'application pratique des technologies web modernes, des pratiques de sécurité, et des principes de développement full-stack avec intégration d'IA.

### Fonctionnalités Principales
- **Authentification & Autorisation Sécurisées**: Système d'authentification JWT avec contrôle d'accès basé sur les rôles
- **Gestion Intelligente des Produits**: CRUD avec upload d'images via Cloudinary et recommandations IA
- **Panier Intelligent**: Gestion temps réel avec recommandations de produits basées sur l'IA
- **Traitement des Commandes**: Gestion complète du cycle de vie avec prédiction ETA de livraison
- **Profils Utilisateurs**: Comptes personnalisables avec historique et préférences
- **Tableau de Bord Admin**: Interface administrative complète
- **Recherche & Filtrage Avancés**: Recherche intelligente avec IA
- **Forum de Recommandations**: Système de recommandations basé sur l'IA pour les discussions
- **Chatbot IA**: Assistant virtuel intégré avec OpenAI GPT
- **Prédictions de Livraison**: ML pour estimer les délais de livraison
- **Design Responsive**: Interface mobile-first moderne

## Technologies utilisées

### Frontend
- **Angular 21.1.0**: Framework frontend moderne basé sur TypeScript
- **RxJS 7.8**: Programmation réactive pour les opérations asynchrones
- **TailwindCSS 3.4**: Framework CSS utility-first pour design responsive
- **Chart.js 4.5**: Graphiques et visualisations interactives
- **Leaflet 1.9**: Cartes interactives pour géolocalisation
- **WebSocket/STOMP**: Communication temps réel
- **Vitest 4.1**: Framework de tests unitaires rapide
- **TypeScript 5.9**: Développement JavaScript type-safe

### Backend
- **Spring Boot 3.3.5**: Framework Java enterprise
- **Spring Security**: Framework d'authentification et autorisation
- **JWT (JSON Web Tokens)**: Authentification sécurisée basée sur les tokens
- **Spring Data MongoDB**: Couche d'accès aux données MongoDB
- **Spring AOP**: Programmation orientée aspect
- **SpringDoc OpenAPI 2.6**: Documentation API (Swagger UI)
- **WebSocket**: Communication temps réel
- **Maven**: Gestion des dépendances et automatisation de build
- **Java 17**: Plateforme Java LTS

### Intelligence Artificielle & Machine Learning
- **Python 3.x**: Langage principal pour les services IA
- **FastAPI**: Framework web pour les APIs ML
- **Pandas & NumPy**: Manipulation et analyse de données
- **Scikit-learn**: Algorithmes de machine learning
- **XGBoost**: Modèles d'ensemble avancés
- **FAISS**: Recherche de similarité vectorielle
- **OpenAI GPT**: Chatbot intelligent
- **Sentence Transformers**: Embeddings pour recommandations

### Base de Données & Stockage
- **MongoDB**: Base de données NoSQL orientée documents
- **Cloudinary**: Stockage et optimisation d'images dans le cloud
- **FAISS Index**: Stockage d'embeddings vectoriels

### Services Externes
- **Twilio**: Service SMS pour notifications
- **Brevo (Sendinblue)**: Service email SMTP
- **OpenAI API**: Intelligence artificielle conversationnelle
- **Cloudinary**: Gestion d'images et médias

### Outils & DevOps
- **Docker**: Containerisation pour déploiement
- **Docker Compose**: Orchestration multi-services
- **Git**: Système de contrôle de version
- **Jenkins**: CI/CD (Fichiers de configuration inclus)
- **Kubernetes**: Configuration K8s pour déploiement
- **Prettier**: Formatage de code

## Architecture

Le projet suit une **architecture microservices** avec séparation claire des responsabilités :

```
┌─────────────────────────────────────────────────────────────┐
│                    Frontend (Angular)                       │
│                     Port 4200                              │
└─────────────────────┬───────────────────────────────────────┘
                      │ HTTP/REST + WebSocket
                      │ (JWT Token)
┌─────────────────────▼───────────────────────────────────────┐
│                Backend (Spring Boot)                        │
│                     Port 8089                              │
│  ┌─────────────────────────────────────────────────────────┐│
│  │ • Controllers  • Services  • Security  • WebSocket     ││
│  │ • Repositories • JWT Auth  • File Upload • Email       ││
│  └─────────────────────────────────────────────────────────┘│
└─────────────────────┬───────────────────────────────────────┘
                      │
         ┌────────────┼────────────────────────────────┐
         │            │                                │
┌────────▼──┐  ┌──────▼──────┐  ┌─────────────────────▼──┐
│ MongoDB   │  │ AI Services │  │   External Services    │
│Port 27017 │  │  (Python)   │  │ • Cloudinary (Images)  │
│           │  │ • Cart AI   │  │ • Twilio (SMS)         │
│ • Users   │  │ • Delivery  │  │ • Brevo (Email)        │
│ • Products│  │ • Forum Rec │  │ • OpenAI (Chatbot)     │
│ • Orders  │  │ • ML Models │  │                        │
└───────────┘  └─────────────┘  └────────────────────────┘
```

### Services IA Intégrés

1. **AI Cart Service** (`ai-cart/`): Recommandations de produits intelligentes
2. **AI Delivery ETA** (`ai-delivery-eta/`): Prédiction des délais de livraison
3. **AI Forum Recommendations** (`ai-forum-recommendation/`): Recommandations de contenu forum
4. **Marketplace ML** (`marketplace-ml/`): Système de recommandations global
5. **ML Service** (`ml-service/`): Services ML centralisés pour covoiturage et négociations

## Prérequis

Avant de lancer le projet, assurez-vous d'avoir installé :

### Obligatoires
- **Java 17** ou supérieur
- **Node.js 18+** et **npm 11+**
- **MongoDB 6+** (local ou Docker)
- **Maven 3.8+** (ou utiliser le wrapper Maven inclus)
- **Python 3.9+** (pour les services IA)
- **Git**

### Optionnels (pour services externes)
- **Docker & Docker Compose** (pour déploiement containerisé)
- **Cloudinary Account** (stockage d'images)
- **Twilio Account** (notifications SMS)
- **OpenAI API Key** (chatbot IA)
- **Brevo Account** (service email)

## Installation

### 1. Cloner le Repository
```bash
git clone https://github.com/[YOUR-USERNAME]/Esprit-PIDEV_SE-4SE2-2526-Espritmarket.git
cd Esprit-PIDEV_SE-4SE2-2526-Espritmarket
```

### 2. Configuration Base de Données
Assurez-vous que MongoDB fonctionne sur `localhost:27017`, ou mettez à jour la chaîne de connexion dans `backend/.env`.

### 3. Configuration Backend
```bash
cd backend
cp .env.example .env
# Éditez .env avec votre configuration
```

### 4. Installation Services IA (Optionnel)
```bash
# Service Cart IA
cd ai-cart
pip install -r requirements.txt

# Service Delivery ETA
cd ../ai-delivery-eta
pip install -r requirements.txt

# Service Forum Recommendations
cd ../ai-forum-recommendation
pip install -r requirements.txt

# ML Service principal
cd ../ml-service
pip install -r requirements.txt
```

## Lancement

### Démarrage Backend (Spring Boot)
```bash
cd backend
# Avec Maven wrapper (recommandé)
./mvnw spring-boot:run
# OU avec Maven installé
mvn spring-boot:run
# OU utiliser le script de lancement
./launch.bat  # Windows
```
**URL**: http://localhost:8089
**Documentation API**: http://localhost:8089/swagger-ui.html

### Démarrage Frontend (Angular)
```bash
cd frontend
# Installation des dépendances
npm install
# Démarrage serveur développement
npm start
```
**URL**: http://localhost:4200

### Démarrage Services IA (Optionnel)
```bash
# Service Cart IA
cd ai-cart
python -m uvicorn app.main:app --reload --port 8001

# Service Delivery ETA  
cd ai-delivery-eta
python -m uvicorn app.main:app --reload --port 8002

# Service Forum Recommendations
cd ai-forum-recommendation
python -m uvicorn app.main:app --reload --port 8003

# ML Service principal
cd ml-service  
python main.py
```

### Démarrage avec Docker (Recommandé pour Production)
```bash
# Construction et démarrage tous services
docker-compose up --build

# Mode détaché
docker-compose up -d

# Arrêt tous services
docker-compose down
```

## Variables d'environnement

### Backend (.env)
```env
# Base de données
MONGODB_URI=mongodb://localhost:27017/esprit_market

# JWT
JWT_SECRET=your-super-secret-jwt-key-min-32-chars
JWT_EXPIRATION_MS=86400000

# Admin
ADMIN_PASSWORD=admin123

# Serveur
SERVER_PORT=8089

# Cloudinary (Images)
CLOUDINARY_CLOUD_NAME=your-cloud-name
CLOUDINARY_API_KEY=your-api-key  
CLOUDINARY_API_SECRET=your-api-secret

# Twilio (SMS)
TWILIO_ACCOUNT_SID=your-account-sid
TWILIO_AUTH_TOKEN=your-auth-token
TWILIO_SERVICE_SID=your-service-sid

# Email (Brevo)
BREVO_SMTP_LOGIN=your-brevo-login
BREVO_SMTP_KEY=your-brevo-key

# OpenAI (Chatbot)
OPENAI_API_KEY=sk-your-openai-api-key
CHATBOT_MODEL=gpt-4o-mini
CHATBOT_ENABLED=true
```

### Services IA (.env pour chaque service)
Consultez les fichiers `.env.example` dans chaque dossier de service IA pour les variables spécifiques.

## Tests

### Tests Frontend
```bash
cd frontend
npm test              # Tests une fois
npm run test:watch    # Tests en mode watch
```

### Tests Backend
```bash
cd backend
mvn test
```

### Tests Services IA
```bash
# Dans chaque dossier de service IA
python -m pytest  # Si des tests sont configurés
```

## Structure du Projet

```
Esprit-PIDEV_SE-4SE2-2526-Espritmarket/
├── backend/                    # Application Spring Boot
│   ├── src/main/java/         # Code source Java
│   ├── src/main/resources/    # Fichiers configuration
│   ├── src/test/              # Tests unitaires
│   ├── pom.xml               # Configuration Maven
│   └── .env.example          # Variables environnement exemple
│
├── frontend/                  # Application Angular
│   ├── src/app/              # Composants, services, guards
│   ├── src/assets/           # Assets statiques
│   ├── package.json          # Dépendances npm
│   ├── angular.json          # Configuration Angular CLI
│   └── tailwind.config.js    # Configuration TailwindCSS
│
├── ai-cart/                  # Service IA recommandations panier
│   ├── app/                  # Code FastAPI
│   ├── models/               # Modèles ML entraînés
│   └── requirements.txt      # Dépendances Python
│
├── ai-delivery-eta/          # Service prédiction livraison
│   ├── app/                  # Code FastAPI
│   ├── artifacts/            # Modèles ML
│   └── data/                 # Datasets
│
├── ai-forum-recommendation/  # Service recommandations forum
│   ├── app/                  # Code FastAPI  
│   ├── artifacts/            # Embeddings et index FAISS
│   └── requirements.txt      # Dépendances Python
│
├── marketplace-ml/           # Service ML marketplace
├── ml-service/               # Services ML centralisés
├── infra/                    # Configuration infrastructure
│   ├── docker-compose.yaml  # Orchestration Docker
│   └── k8s/                  # Manifests Kubernetes
│
└── datasets/                 # Datasets pour ML
```

## Démo

### Fonctionnalités Disponibles
- **Inscription/Connexion** avec authentification JWT
- **Navigation produits** avec recherche intelligente
- **Panier intelligent** avec recommandations IA
- **Processus de commande** complet avec prédiction livraison
- **Tableau de bord utilisateur** avec historique
- **Interface admin** pour gestion complète
- **Forum communautaire** avec recommandations
- **Chatbot IA** pour assistance client
- **Notifications temps réel** via WebSocket

### URLs de Démonstration
- **Frontend**: http://localhost:4200
- **Backend API**: http://localhost:8089
- **Documentation API**: http://localhost:8089/swagger-ui.html
- **Services IA**: Ports 8001-8003 (selon services activés)

## Auteurs

Ce projet a été développé par une équipe d'étudiants de 4ème année d'Ingénierie à l'ESPRIT :

- **Zekri Farah** - Développement Frontend & UX
- **Tessnim Bouzekri** - Développement Backend & Sécurité  
- **Mohamed Amine Shili** - Intelligence Artificielle & ML
- **Feriel Guesmi** - Base de données & APIs
- **Eya Weslati** - Tests & Qualité
- **Ameni Makdouli** - DevOps & Déploiement

### Contexte Académique
- **Institution**: École Supérieure Privée d'Ingénierie et de Technologies (ESPRIT) – Tunisie
- **Programme**: PIDEV (Projet Intégré de Développement) – 4ème Année Ingénierie
- **Classe**: 4SE2
- **Année Académique**: 2025–2026
- **Objectif**: Développer une application web full-stack avec IA démontrant la maîtrise du développement logiciel moderne, collaboration d'équipe et gestion de projet

## Sécurité

- Authentification JWT avec tokens d'accès et de rafraîchissement
- Chiffrement des mots de passe avec BCrypt
- Configuration CORS pour communication frontend-backend
- Validation et sanitisation des entrées
- Contrôle d'accès basé sur les rôles (USER, ADMIN, VENDOR)
- Sécurisation des clés API et secrets via variables d'environnement
- Protection contre les injections et attaques courantes

## API Endpoints

### Authentification
- `POST /api/auth/login` - Connexion utilisateur
- `POST /api/auth/register` - Inscription utilisateur  
- `POST /api/auth/refresh` - Rafraîchissement token

### Gestion Utilisateurs
- `GET /api/users` - Liste utilisateurs (Admin)
- `GET /api/users/{id}` - Détails utilisateur
- `PUT /api/users/{id}` - Mise à jour profil

### Produits & Marketplace
- `GET /api/products` - Liste produits avec pagination
- `POST /api/products` - Créer produit (Vendor/Admin)
- `GET /api/products/{id}` - Détails produit
- `PUT /api/products/{id}` - Modifier produit

### Commandes
- `POST /api/orders` - Créer commande
- `GET /api/orders` - Historique commandes
- `GET /api/orders/{id}` - Détails commande

### Services IA
- `POST /api/ai/cart/recommend` - Recommandations panier
- `POST /api/ai/delivery/predict` - Prédiction ETA livraison
- `POST /api/ai/forum/recommend` - Recommandations forum
- `POST /api/chatbot/message` - Interaction chatbot

**Documentation complète**: http://localhost:8089/swagger-ui.html

## Déploiement

### Environnement de Développement
```bash
# Lancement rapide avec Docker
docker-compose -f docker-compose.dev.yml up
```

### Environnement de Production
```bash
# Build et déploiement production
docker-compose -f docker-compose.prod.yml up -d

# Avec Kubernetes
kubectl apply -f infra/k8s/
```

## Remerciements

Nous tenons à exprimer notre gratitude à :

- **L'École Supérieure Privée d'Ingénierie et de Technologies (ESPRIT)** pour le cadre académique et les ressources
- Nos **superviseurs et enseignants PIDEV** pour leurs conseils et soutien tout au long du projet
- La **communauté open-source** pour les excellents frameworks et bibliothèques qui ont rendu ce projet possible
- **OpenAI, Cloudinary, Twilio, et Brevo** pour leurs services qui enrichissent notre plateforme

---

**Développé avec ❤️ à l'ESPRIT – Tunisie | PIDEV 4SE2 | 2025–2026**

*Une marketplace intelligente qui combine e-commerce moderne et intelligence artificielle pour une expérience utilisateur exceptionnelle.*
