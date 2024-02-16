---
title: "Installer detect-secrets en pre-commit"

description: "Installation de detect-secrets pour les pre-commit"

featured_image: '/images/detect_secret.webp'
---

#Intégration de Detect Secret dans vos workflows : Un must pour la sécurité
Detect Secret est un outil vital pour sécuriser vos projets en prévenant l'exposition accidentelle de secrets, que ce soit des clés API,des mots de passe... dans vos dépôts git. Découvrons comment l'utiliser efficacement avec un hook de pre-commit.

##Detect Secret : 
 Detect Secret est conçu pour identifier automatiquement les secrets dans le code avant qu'ils n'atteignent un dépôt distant. Il sert de garde-fou contre la fuite de données sensibles de manière locale.

##Fonctionnement :
Detect Secret fonctionne en scannant les fichiers à la recherche de motifs qui ressemblent à des secrets. Il se sert de plusieurs types d'analyses pour détecter tous les secrets potentiels

###Analyse Heuristique
Détecteurs de Signature: Detect Secret utilise des détecteurs spécifiques pour identifier les signatures courantes de secrets, comme les formats de clés API ou les tokens JWT.
Règles de Détecteurs: Il applique des règles heuristiques pour évaluer si une chaîne de caractères correspond à un secret potentiel, réduisant ainsi les faux positifs.
###Audit et Validation
**Audit Manuel:** Après la détection, les développeurs peuvent auditer manuellement les résultats, marquant les véritables secrets pour prévenir leur divulgation.
Validation Automatique: Dans certains cas, Detect Secret peut automatiquement valider l'authenticité d'un secret en utilisant des vérifications de format ou en se connectant à des services externes (selon la configuration).
##Intégration avec pre-commit
L'intégration de Detect Secret dans le workflow de pre-commit permet d'automatiser la détection des secrets au moment du commit, garantissant qu'aucun secret ne quitte votre environnement de développement.

##Installation :
Installez pre-commit et detect-secrets via pip.

```
pip install pre-commit 
pip install detect-secrets
```
Creez ensuite un fichier .pre-commit-config.yaml avec la configuration suivante :
```
repos:
  - repo: https://github.com/Yelp/detect-secrets
    rev: v1.4.0  # Use the appropriate version
    hooks:
      - id: detect-secrets
        args: ['--baseline', '.secrets.baseline']
        exclude: .*/tests/.*
```
**Note :** Il est important de choisir la bonne version de detect-secrets, ici la version 1.4.0 est la plus récente dans mon cas.

Il nous faut désormais générer le fichier .secrets.baseline. Pour cela vous pouvez entrer les commandes suivantes :

```
detect-secrets scan > .secrets.baseline
```
**Attention:** Pour fonctionner il est nécessaire de bien sauvegarder le fichier .secrets.baseline en UTF-8.
Une fois le fichier .pre-commit-config.yaml correctement configuré, et le fichier .secrets.baseline créé, vous pouvez utiliser la commande suivante pour activer le pré-commit :
```
pre-commit install
```
Chaque commit déclenchera désormais une analyse à la recherche de secrets, empêchant leur inclusion accidentelle.

L'intégration de Detect Secret augmente la sécurité de vos projets en identifiant et en prévenant les fuites de secrets. C'est une étape proactive essentielle pour maintenir la confiance et la sûreté de vos applications et de leurs utilisateurs.
Il est cependant important de noter que Detect Secret ne fonctionne qu'en local et qu'il sera donc nécessaire à tous les utilisateurs de l'installer pour en bénéficier.