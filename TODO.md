- [ ] Ajouter du contenu sur les certifs etc de manière cool pas dans l'index
- [ ] Replace Gaspard name with real one
- [ ] Add identiy in secrets for every occurence 
- [ ] Do not forget linkedIn
- [x] Activer l'authentification à deux facteurs (2FA) pour tous les utilisateurs** : Assurez-vous que tous les contributeurs du repository ont activé l'authentification à deux facteurs sur leur compte GitHub, augmentant ainsi la sécurité contre les accès non autorisés.

###Disponible seulement pour les applications

- [ ] Utiliser les secrets GitHub pour stocker les variables d'environnement** : Stockez les clés API, les mots de passe et autres secrets en utilisant les secrets GitHub au lieu de les hardcoder dans les fichiers de configuration. GitHub Actions peut accéder à ces secrets de manière sécurisée sans les exposer dans le code.

- [ ] Restreindre les branches qui peuvent déclencher des workflows** : Configurez les workflows GitHub Actions pour qu'ils ne s'exécutent que sur des branches spécifiques (comme main ou develop) afin d'éviter l'exécution de code malveillant introduit dans des branches non protégées.

- [ ] Utiliser des politiques de branch protection** : Configurez des règles de protection des branches pour votre branche principale et toute autre branche critique. Cela peut inclure l'exigence de revues de code, de statuts de vérification réussis avant la fusion, et l'interdiction de pousser directement.

- [ ] Réviser régulièrement les accès** : Examinez et gérez régulièrement les droits d'accès des utilisateurs et des intégrations tierces. Supprimez les accès inutilisés ou obsolètes pour minimiser les risques de sécurité.

- [ ] Mettre à jour régulièrement les dépendances** : Utilisez des outils comme Dependabot pour garder automatiquement les dépendances de votre projet à jour et réduire les vulnérabilités liées à des bibliothèques obsolètes.

- [ ] Effectuer des audits de sécurité** : Utilisez des outils d'analyse de code et de sécurité, tels que CodeQL (intégré à GitHub) pour scanner régulièrement votre code à la recherche de vulnérabilités.

- [ ] Sécuriser les déploiements** : Assurez-vous que le processus de déploiement est sécurisé, en utilisant des clés SSH ou des tokens d'accès personnel avec les permissions minimales nécessaires pour déployer le site.

- [ ] Utiliser des runners auto-hébergés de manière sécurisée** : Si vous utilisez des runners GitHub Actions auto-hébergés pour des raisons de performances ou de confidentialité, assurez-vous qu'ils sont sécurisés et isolés des environnements sensibles.

10. **Former et sensibiliser** : Sensibilisez les contributeurs aux meilleures pratiques de sécurité, y compris la gestion sécurisée des secrets, la reconnaissance des injections de code malveillant dans les pull requests, et l'importance des revues de code.

1- [ ] Examiner régulièrement les logs d'audit** : Gardez un œil sur les logs d'audit GitHub pour détecter les comportements anormaux ou les accès non autorisés