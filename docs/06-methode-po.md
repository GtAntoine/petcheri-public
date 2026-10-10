# Méthode Product Owner

Quatre mois, trois surfaces, près de 500 commits : ce rythme ne tient qu'avec une méthode qui rend chaque décision écrite, vérifiable et réutilisable, par l'équipe comme par les agents IA avec lesquels je développe.

## Du besoin au ticket

1. **Le besoin arrive** d'un concierge, de la comptabilité, du marketing ou d'un audit. Il est posé dans le tableau du sprint (Notion).
2. **Le ticket est challengé** avant d'être développé : une section « Challenge » questionne le besoin (est-ce le bon problème ? existe-t-il déjà quelque chose ? que se passe-t-il pour les données existantes ?), une section « Tests à faire » liste ce qui prouvera que c'est fini. PACO rédige les tickets dans ce format.
3. **La règle avant l'écran.** Pour tout ce qui touche à l'argent ou aux droits, la règle est écrite et testée avant que l'écran soit dessiné.
4. **Livraison sur staging** (copie anonymisée de la production), recette, puis production. Le déploiement ne joue jamais les migrations de base : elles partent à part, une fois vérifiées.

## Les specs fonctionnelles

98 pages décrites **telles qu'elles sont codées** : rôles qui y accèdent, données lues, champs (types, bornes, conditions), actions et leurs effets (statuts, e-mails, historique, batchs). Chaque spec finit par ses questions ouvertes et ses anomalies.

Règle : une évolution de page met à jour sa spec dans la même livraison. Une spec qui ment fait plus de dégâts qu'une spec absente.

## Le programme d'audits

Douze audits, chacun lancé à partir d'une fiche (outils à utiliser, référentiel, format du livrable) :

| Audit | Question posée |
|---|---|
| Sécurité | Qui peut lire ou écrire quoi, et le vérifie-t-on vraiment ? |
| Intégrité des données | La base dit-elle la même chose que les écrans ? |
| Specs détaillées | Chaque page est-elle décrite ? |
| Workflows et champs | Chaque statut a-t-il une sortie, chaque champ un usage ? |
| Contradictions | Deux écrans disent-ils deux choses différentes ? |
| Légal et RGPD | CGV, consentements, conservation, sous-traitants |
| UX, UI, accessibilité | Heuristiques, contrastes, cibles tactiles, clavier |
| Dépendances et dette | Paquets vulnérables, abandonnés, inutilisés |
| Exploitation | Batchs, tâches planifiées, configuration par environnement |
| Performance et coûts | Temps de chargement, poids des pages, coût de l'IA |
| Synchronisation | Le code, les specs et la documentation disent-ils la même chose ? |
| Vitrine | SEO, visibilité dans les moteurs IA, accessibilité |

Règles communes : lecture seule, requêtes SQL en `SELECT` sur la copie anonymisée seulement, aucun mot de passe tapé sur un site distant. Un audit **constate**, il ne corrige rien : les 169 constats sont classés par gravité et deviennent des tickets, priorisés comme le reste du backlog.

## Travailler avec des agents IA

Je développe avec Claude Code. Ce qui rend ce travail fiable :

- **Un fichier de règles du projet** tenu à jour : architecture, conventions, pièges connus (le serveur de production refuse certains modules natifs, une colonne JSON revient en texte), règles métier non négociables. Chaque piège rencontré une fois y est écrit pour ne pas être rencontré deux fois.
- **Des compétences dédiées** : une pour lancer les audits dans le format maison, une pour challenger un ticket.
- **Des tests sur les règles sensibles** plutôt que sur les écrans : 465 tests unitaires sur les droits, les calculs financiers, les avoirs, les champs modifiables et les garde-fous de l'assistant.
- **Une relecture humaine de tout ce qui sort** : une capture, un e-mail, un document client.

## Rendre l'outil explicable

- **Des tutoriels Notion**, accessibles depuis un bouton « Tutoriels » posé sur chaque écran de l'équipe qui en a un.
- **Des tutoriels vidéo** générés depuis l'application : un script, des captures refaites par programme (vrais noms remplacés, photos floutées, écritures bloquées), une voix de synthèse et une caméra qui suit la phrase. Un écran qui change fait relancer les captures, pas un tournage.
- **Une page `/design`** pour expliquer la charte à quelqu'un qui n'a pas accès au code.
- **Un catalogue des e-mails** qui liste chaque envoi, ses paramètres et le fichier qui le déclenche, avec un banc d'essai pour en recevoir un exemplaire.
