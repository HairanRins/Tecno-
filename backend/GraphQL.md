# GraphQL

GraphQL est un langage de requête et un runtime pour les APIs, développé par Facebook en 2012 et rendu open source en 2015. Il offre une alternative aux APIs REST traditionnelles en permettant aux clients de demander exactement les données dont ils ont besoin.

## Principe fondamental

Contrairement à REST où chaque endpoint retourne une structure de données fixe, GraphQL expose un seul endpoint qui accepte des requêtes décrivant précisément les données souhaitées. Le serveur répond en renvoyant uniquement ces données, dans la structure demandée.

## Fonctionnement technique

GraphQL repose sur un système de types strict défini dans un schéma. Ce schéma décrit toutes les données disponibles, leurs relations et les opérations possibles. Les requêtes sont validées contre ce schéma avant exécution.

Les trois types d'opérations principales sont les queries (lecture), mutations (écriture) et subscriptions (temps réel). Chaque champ dans une requête est résolu par une fonction resolver côté serveur.

## Cas d'usage principaux

**Applications mobiles** : GraphQL excelle pour les apps mobiles où la bande passante est limitée. Les développeurs peuvent récupérer exactement les données nécessaires pour chaque écran, réduisant la taille des réponses et améliorant les performances.

**Interfaces complexes** : Pour les tableaux de bord ou applications avec de nombreux composants affichant des données différentes, GraphQL permet de récupérer toutes les données nécessaires en une seule requête plutôt que de faire plusieurs appels REST.

**Architecture microservices** : GraphQL peut servir de couche d'agrégation unifiant plusieurs services backend, permettant aux clients d'accéder à des données provenant de différents services via une seule API.

**Applications temps réel** : Les subscriptions GraphQL facilitent l'implémentation de fonctionnalités temps réel comme les notifications, chats ou mises à jour live.

## Exemples concrets d'usage

**E-commerce** : Une page produit peut récupérer en une requête les détails du produit, les avis clients, les produits similaires et les informations de stock. Avec REST, cela nécessiterait typiquement 3-4 appels séparés.

**Réseaux sociaux** : Un feed peut charger les posts, les informations des auteurs, les nombres de likes et commentaires en une seule requête, optimisant l'affichage et réduisant les temps de chargement.

**Applications financières** : Un dashboard peut afficher simultanément le solde des comptes, l'historique des transactions récentes et les graphiques de performance via une requête unique et personnalisée.

**Plateformes de contenu** : Netflix ou Spotify utilisent GraphQL pour que leurs applications mobiles et web récupèrent exactement les métadonnées nécessaires pour chaque vue (listes, détails, recommandations).

## Avantages clés

GraphQL élimine le problème de sur-récupération (récupérer trop de données) et sous-récupération (nécessiter plusieurs requêtes) des APIs REST. Il offre également une meilleure expérience développeur avec des outils d'introspection permettant d'explorer l'API directement.

La forte typologie et l'auto-documentation intégrée facilitent la collaboration entre équipes frontend et backend. Les développeurs frontend peuvent comprendre et utiliser l'API sans documentation externe extensive.

## Entreprises utilisatrices

GitHub utilise GraphQL pour son API publique, permettant aux développeurs de récupérer précisément les données de repositories nécessaires. Shopify l'emploie pour son API e-commerce, Facebook pour ses applications mobiles, et de nombreuses startups l'adoptent pour leurs nouvelles applications.

GraphQL représente une évolution naturelle des APIs, particulièrement adaptée aux besoins modernes d'applications riches et performantes nécessitant une gestion fine des données.
