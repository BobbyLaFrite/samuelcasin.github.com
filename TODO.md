- [ ] Ajouter du contenu sur les certifs etc de manière cool pas dans l'index
- [ ] Replace Gaspard name with real one
- [ ] Add identiy in secrets for every occurence 
- [ ] Do not forget linkedIn
- [x] Activer l'authentification à deux facteurs (2FA) pour tous les utilisateurs** : Assurez-vous que tous les contributeurs du repository ont activé l'authentification à deux facteurs sur leur compte GitHub, augmentant ainsi la sécurité contre les accès non autorisés.

###Disponible seulement pour les applications

- [ ] Utiliser les secrets GitHub pour stocker les variables d'environnement** : Stockez les clés API, les mots de passe et autres secrets en utilisant les secrets GitHub au lieu de les hardcoder dans les fichiers de configuration. GitHub Actions peut accéder à ces secrets de manière sécurisée sans les exposer dans le code.

- [x] Restreindre les branches qui peuvent déclencher des workflows** : Configurez les workflows GitHub Actions pour qu'ils ne s'exécutent que sur des branches spécifiques (comme main ou develop) afin d'éviter l'exécution de code malveillant introduit dans des branches non protégées.

- [x] Utiliser des politiques de branch protection** : Configurez des règles de protection des branches pour votre branche principale et toute autre branche critique. Cela peut inclure l'exigence de revues de code, de statuts de vérification réussis avant la fusion, et l'interdiction de pousser directement.

de plus les commits peuvent se faire uniquement avec une authentifation signée (connexion GPG)



# DONE
* Activer la protection de la branch main
* Enlever le bypass pour les admins
* Activer github actions et le build de hugo directement
* Authoriser seulement le push de la part de personnes signées (GPG par exemple)
* Activer un 2FA avec empreinte digitale
* modification d'un prehook pour match des regex en cours
* ajouter un script local pour empecher de publier des secrets enligne de manière preventive
* signature GPG effectué sur le PC test TESTv2
aaaaa
