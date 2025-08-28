# Des termes importants à savoir 

## 🔑 Les principaux termes en développement

### 1. **Runtime**

* **Définition** : environnement d’exécution dans lequel un programme tourne.
* Il inclut tout ce qu’il faut pour que le code fonctionne : gestion de la mémoire, garbage collector, librairies de base.
* **Exemple** :

  * **Java Runtime Environment (JRE)** → permet d’exécuter des programmes Java compilés.
  * **Node.js Runtime** → permet d’exécuter du JavaScript en dehors du navigateur.
* **Use case** : Tu écris du code en **TypeScript**, tu le compiles en **JavaScript**, puis ce JS tourne dans le **runtime Node.js**.

---

### 2. **SDK (Software Development Kit)**

* **Définition** : kit d’outils fourni pour développer avec une technologie précise.
  Souvent il contient : API, librairies, exemples de code, outils de compilation, documentation.
* **Exemple** :

  * **Android SDK** → tout ce qu’il faut pour développer une app Android (outils de build, émulateur, etc.).
  * **AWS SDK for JavaScript** → permet de manipuler les services AWS directement en JS.
* **Use case** : tu veux intégrer **Google Maps** dans ton app mobile → tu installes le **Google Maps SDK** pour Android/iOS.

---

### 3. **API (Application Programming Interface)**

* **Définition** : ensemble de fonctions, classes ou endpoints qu’un logiciel expose pour interagir avec lui.
* **Exemple** :

  * L’API de Twitter → te permet de poster des tweets depuis ton app.
  * L’API DOM du navigateur → te permet de manipuler les éléments HTML avec JavaScript.
* **Use case** : une app météo utilise l’**API d’OpenWeather** pour récupérer la température d’une ville.

---

### 4. **Framework**

* **Définition** : structure de base qui impose une façon de coder (squelette + conventions + outils intégrés).
* **Exemple** :

  * **React Native** → framework pour faire des apps mobiles cross-platform.
  * **NestJS** → framework backend basé sur Node.js.
* **Use case** : au lieu de tout coder à la main, tu utilises **Django** (framework Python) qui gère déjà les routes, l’ORM, l’authentification.

---

### 5. **Library (ou librairie)**

* **Définition** : ensemble de fonctions ou de classes réutilisables, sans imposer de structure.
* **Exemple** :

  * **Lodash** en JS → fonctions utilitaires (tri, manipulation d’objets).
  * **NumPy** en Python → calcul scientifique.
* **Use case** : tu veux juste faire du calcul math avancé en Python → tu ajoutes **NumPy** à ton projet.

---

### 6. **Compiler / Interpreter**

* **Compiler** → traduit le code source en langage machine avant exécution. (Ex : C, C++)
* **Interpreter** → lit et exécute le code directement sans compilation préalable. (Ex : Python, JavaScript)
* **Use case** :

  * C → ton code est **compilé** → exécutable rapide.
  * Python → ton code est **interprété** → plus lent mais plus flexible.

---

### 7. **Build**

* **Définition** : processus qui transforme ton code source en une version exécutable/optimisée (compilation, minification, bundling, etc.).
* **Exemple** :

  * En React, un `npm run build` génère une version optimisée du site.
  * En Java, `javac` compile en **bytecode** qui sera exécuté dans le runtime.
* **Use case** : avant de déployer ton site web, tu fais un **build** pour réduire la taille des fichiers.

---

### 8. **CLI (Command Line Interface)**

* **Définition** : outil en ligne de commande pour exécuter des tâches.
* **Exemple** :

  * `git` est une CLI pour gérer ton code source.
  * `npm` est une CLI pour installer des paquets JS.
* **Use case** : tu tapes `npm install express` → CLI installe la librairie.

---

### 9. **IDE (Integrated Development Environment)**

* **Définition** : logiciel complet pour coder avec éditeur + debugger + gestion de projet.
* **Exemple** :

  * VS Code, IntelliJ IDEA, PyCharm.
* **Use case** : tu codes ton app Java dans **IntelliJ** qui compile et exécute directement ton projet.

---

### 10. **Container**

* **Définition** : environnement isolé qui contient ton application + ses dépendances.
* **Exemple** :

  * **Docker** → crée des containers pour faire tourner ton app sur n’importe quelle machine.
* **Use case** : tu développes une app sur Windows mais tu veux la déployer sur Linux → tu utilises **Docker**.

---

📌 En résumé :

* **Runtime** = là où le programme s’exécute.
* **SDK** = kit complet pour développer.
* **API** = interface pour interagir.
* **Framework** = squelette qui impose une structure.
* **Library** = boîte à outils réutilisable.
* **Compiler/Interpreter** = traduit ou exécute ton code.
* **Build** = étape de transformation du code.
* **CLI** = outil en ligne de commande.
* **IDE** = environnement de développement complet.
* **Container** = environnement isolé pour ton app.

---

Veux-tu que je te fasse aussi un **schéma visuel simplifié** qui relie tous ces termes (genre mindmap) 📊 ?
