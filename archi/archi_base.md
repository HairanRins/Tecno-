# Architecture logicielle 

Voici un aperçu des **architectures logicielles** les plus connues, dont l'architecture **hexagonale**, avec pour chacune : une **explication**, un **exemple** et les **cas d'utilisation** adaptés.

---

## 🧱 1. Architecture en couches (Layered Architecture)

### 🔹 Explication
L'architecture en couches sépare l'application en couches hiérarchiques (généralement 4) :
- Présentation (UI)
- Application (logique métier)
- Domaine (règles métier)
- Infrastructure (accès aux données, réseau…)

Chaque couche ne dépend que de la couche située directement en dessous.

### 🔹 Exemple
Une application web où :
- Le **frontend** appelle un **contrôleur** (couche présentation),
- Qui appelle un **service** (couche application),
- Qui appelle un **repository** (infrastructure pour accéder à une base de données).

### 🔹 Cas d'utilisation
- Projets d’entreprise classiques (CRM, ERP…)
- Facile à comprendre et à structurer
- Idéal pour des équipes débutantes ou des projets simples

---

## 🔷 2. Architecture hexagonale (Hexagonal / Ports and Adapters)

### 🔹 Explication
Imaginée par **Alistair Cockburn**, elle met le **domaine au centre**, entouré de **ports (interfaces)**, puis d’**adapters** (implémentations concrètes, comme REST, CLI, DB, etc.).

Elle favorise l’indépendance de l’application vis-à-vis de la technologie.

**Principe clé** : "Le monde extérieur s’adapte à l’application, pas l’inverse."

### 🔹 Exemple
Un système de gestion d’ordres :
- Le **core domain** gère les règles métier (ex. : créer une commande),
- Il expose un **port** `CreateOrderPort`,
- Plusieurs **adapters** peuvent utiliser ce port :
  - Un contrôleur REST
  - Une commande CLI
  - Un listener Kafka
  - Une implémentation de base de données

### 🔹 Cas d'utilisation
- Applications orientées domaine
- Besoin de tests automatisés faciles
- Volonté de changer facilement de technologie (ex. : base de données, transport HTTP…)

---

## 🌀 3. Architecture en oignon (Onion Architecture)

### 🔹 Explication
Semblable à l’hexagonale mais plus formel sur la séparation :
- Le cœur (Entities)
- Application Services
- Infrastructure en dehors

**Règle stricte** : les dépendances vont de l’extérieur vers l’intérieur, jamais l’inverse.

### 🔹 Exemple
Une application e-commerce :
- **Domain** : `Order`, `Product`, `Customer`
- **Application** : `OrderService`
- **Interface** : `OrderRepository`
- **Infrastructure** : `PostgresOrderRepository`

### 🔹 Cas d'utilisation
- Domain-Driven Design (DDD)
- Grands projets avec logique métier complexe

---

## 🧠 4. Clean Architecture (Robert C. Martin aka Uncle Bob)

### 🔹 Explication
Unifie plusieurs concepts (hexagonale, oignon…) :
- Entities (core)
- Use Cases
- Interface Adapters (Controllers, Presenters)
- Frameworks & Drivers (UI, DB, etc.)

**Règle d’or** : dépendances dirigées vers l’intérieur.

### 🔹 Exemple
Une API de réservation :
- **Use case** : `BookFlightUseCase`
- **Input boundary** : une interface que le contrôleur appelle
- **Output boundary** : interface pour envoyer les données à une base ou un message Kafka

### 🔹 Cas d'utilisation
- Grands projets modifiables, testables et maintenables
- Environnements avec plusieurs interfaces (web, mobile, API…)

---

## ☁️ 5. Microservices Architecture

### 🔹 Explication
Chaque composant (service) est une application autonome, avec sa propre base de données, API, logique métier.

Les services communiquent entre eux (souvent via HTTP ou messaging comme Kafka/RabbitMQ).

### 🔹 Exemple
- Un service `User`, un service `Order`, un service `Inventory`
- Chacun déployé indépendamment
- Un front envoie des appels aux différents services

### 🔹 Cas d'utilisation
- Équipes nombreuses et autonomes
- Systèmes à haute scalabilité
- Grands projets distribués (Amazon, Netflix…)

---

## 📚 Récapitulatif

| Architecture        | Focus principal        | Idéale pour…                               |
|---------------------|-------------------------|--------------------------------------------|
| En couches          | Séparation technique     | Projets simples et classiques              |
| Hexagonale          | Isolation métier         | Tests faciles, ports/adaptateurs multiples |
| Oignon              | Séparation stricte       | DDD et gros projets métier                 |
| Clean Architecture  | Flexibilité + testabilité| Long terme, multi-interfaces               |
| Microservices       | Indépendance des modules | Scalabilité et indépendance forte          |

---

