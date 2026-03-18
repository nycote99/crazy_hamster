# Politique de Sécurité - Crazy Hamster 🐹

## Engagement de Sécurité
Bien que **Crazy Hamster** soit un projet de divertissement et d'apprentissage, la sécurité des utilisateurs et l'intégrité du code sont des priorités. Ce projet est conçu selon le principe de "Sécurité par la simplicité".

## Versions Supportées
Seule la version la plus récente (main branch) bénéficie de mises à jour de sécurité.

| Version | Supportée |
| ------- | --------- |
| 1.0.x   | ✅ Oui     |
| < 1.0   | ❌ Non     |

## Ce qui est protégé
1. **Zéro Collecte de Données** : L'application n'utilise aucun cookie tiers, aucun tracker et aucune base de données distante. Toutes les données (positions dans le labyrinthe, état du timer) restent dans la mémoire vive de votre navigateur.
2. **Exécution Locale** : Le code est du JavaScript Vanille s'exécutant côté client (Client-Side). Aucun script n'est exécuté sur un serveur distant.
3. **Protection des Secrets** : Le fichier `.gitignore` du projet est configuré pour empêcher la fuite accidentelle de fichiers sensibles (clés SSH, fichiers de configuration système).

## Signaler une vulnérabilité
Si vous découvrez une faille de sécurité ou un comportement anormal, merci de ne pas ouvrir d'Issue publique. 

Veuillez signaler toute vulnérabilité de manière confidentielle via :
* **GitHub Private Vulnerability Reporting** (si activé sur ce dépôt).
* Ou en contactant le mainteneur via les informations présentes sur son profil GitHub.

Une réponse vous sera adressée sous 48 à 72 heures.

## Bonnes Pratiques recommandées
Pour une sécurité optimale lors de l'utilisation ou de la modification de ce projet :
* N'utilisez que des clones provenant du dépôt officiel.
* Si vous hébergez votre propre version sur **GitHub Pages**, assurez-vous que l'option "Enforce HTTPS" est activée dans les paramètres de votre dépôt.
