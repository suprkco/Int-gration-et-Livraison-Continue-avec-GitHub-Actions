# TP2 - cicd

## Questions 

1. What are testcontainers ?

Les testcontainers sont des bibliothèques Java qui permettent d'exécuter des conteneurs Docker pendant les tests. 
Dans le contexte décrit, ils sont utilisés pour lancer un conteneur PostgreSQL pendant l'exécution des tests, fournissant ainsi une base de données dans laquelle les tests peuvent insérer ou extraire des données, garantissant ainsi que les fonctionnalités d'interaction avec la base de données de l'application fonctionnent comme prévu.

2. Document your Github Actions configurations.

GitHub Actions est un service intégré à GitHub qui permet d'automatiser des workflows, comme la construction, les tests et le déploiement de votre code. Dans le contexte fourni, GitHub Actions est configuré pour:

- Être déclenché lors des push et des pull requests.
- Exécuter les jobs sur une machine virtuelle Ubuntu 22.04.
- Récupérer le code source du dépôt.
- Configurer JDK 17.
- Construire l'application et exécuter les tests avec Maven.
- Si les tests sont réussis, construire et pousser des images Docker vers Docker Hub.

La configuration utilise également des variables sécurisées pour stocker les informations d'identification de Docker Hub, garantissant que ces informations sensibles ne sont pas exposées.

Tout cela est défini dans le fichier main.yml sous le répertoire .github/workflows du dépôt. Ce fichier YAML décrit étape par étape comment le workflow doit s'exécuter, en utilisant à la fois des actions prédéfinies fournies par GitHub et des commandes personnalisées.