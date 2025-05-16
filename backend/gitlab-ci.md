# GitLab CI/CD

**GitLab CI/CD** avec le fichier `.gitlab-ci.yml`, accompagnée d'un exemple commenté.

---

## **1. Qu'est-ce que GitLab CI/CD ?**

**GitLab CI/CD** est un outil d'intégration continue et de déploiement continu (CI/CD) intégré à GitLab. Il permet d'automatiser les étapes comme :

* Les tests
* La construction (build)
* Le déploiement

Le tout est défini dans un fichier nommé **`.gitlab-ci.yml`** placé à la racine du dépôt.

---

## **2. Fonctionnement général**

1. **Git push** : À chaque push, GitLab lit `.gitlab-ci.yml`.
2. **Pipeline** : GitLab déclenche un pipeline composé de jobs.
3. **Runner** : Les jobs sont exécutés par des **runners GitLab** (agents exécutant les tâches sur une machine).
4. **Étapes (stages)** : Les jobs peuvent être ordonnés en étapes (build, test, deploy…).

---

## **3. Structure d’un `.gitlab-ci.yml`**

### Exemple complet avec explications :

```yaml
# 1. Définition des étapes
stages:
  - build
  - test
  - deploy

# 2. Job de build
build-job:
  stage: build
  script:
    - echo "Compilation de l'application"
    - npm install
    - npm run build
  only:
    - main  # Ce job s'exécute uniquement sur la branche main

# 3. Job de test
test-job:
  stage: test
  script:
    - echo "Exécution des tests"
    - npm run test
  except:
    - tags  # Ne s'exécute pas sur les tags

# 4. Job de déploiement
deploy-job:
  stage: deploy
  script:
    - echo "Déploiement de l'application"
    - ./deploy.sh
  environment:
    name: production
    url: https://monapp.example.com
  only:
    - tags  # S’exécute uniquement lors du push d’un tag
```

---

## **4. Explication des éléments**

| Élément           | Description                                                               |
| ----------------- | ------------------------------------------------------------------------- |
| `stages`          | Liste des étapes dans l’ordre d’exécution.                                |
| `job-name`        | Nom du job.                                                               |
| `stage`           | À quelle étape appartient ce job.                                         |
| `script`          | Liste de commandes à exécuter.                                            |
| `only` / `except` | Définir quand le job doit être exécuté (par branche, tag, etc.).          |
| `environment`     | Spécifie l’environnement de déploiement (utile pour GitLab Environments). |

---

## **5. Exemple minimal pour projet Node.js**

```yaml
stages:
  - test

test:
  stage: test
  image: node:18
  script:
    - npm install
    - npm test

