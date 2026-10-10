# Vision et contexte

## Le problème

Faire garder son animal, c'est confier un membre de la famille à un inconnu. Les grandes plateformes de mise en relation règlent la logistique (trouver quelqu'un de libre, payer) mais laissent le propriétaire seul pour juger de la confiance.

Pet Cheri se place sur l'autre bout du marché : une **conciergerie**. Une équipe sélectionne les prestataires, choisit le bon pour chaque animal, suit la mission et répond quand quelque chose se passe. Le client paie pour ce suivi, et pour une expérience à la hauteur.

C'est ce qui rendait la première version de l'outil insuffisante : elle couvrait la logistique, mais rien dans l'interface ne disait « premium ». Le site vitrine promettait une conciergerie qui chouchoute, l'application ressemblait à un formulaire administratif.

## Les utilisateurs

| Qui | Ce qu'il attend | Où il vit dans le produit |
|---|---|---|
| **Le propriétaire** | Décrire son besoin vite, savoir où en est sa demande, être rassuré | Vitrine, tunnel `/demande`, espace client, PACO, application mobile |
| **Le prestataire** (« chouchouteur ») | Recevoir des missions qui lui correspondent, déclarer ce qu'il a fait, être payé | Espace prestataire, relevé mensuel, application mobile |
| **Les concierges** | Trouver le bon prestataire, suivre chaque demande, relancer au bon moment | Espace équipe : demandes, carte, fiches, PACO |
| **La comptabilité** | Des notes justes, figées une fois émises, un journal exploitable par l'expert-comptable | Facturation, avoirs, journal des ventes, tableaux de bord |
| **Le marketing** | Des pages qui se trouvent sur Google, des e-mails qui partent au bon moment, une charte qu'on peut confier à un prestataire extérieur | Vitrine, annonces, e-mails, page `/design` |

Cinq profils, trois surfaces : la difficulté n'était pas de servir chacun, mais de garder un seul produit cohérent entre eux.

## Ce que montrait l'ancien site

Avant de reconstruire la vitrine, j'ai audité son contenu page par page. Quelques constats :

- **Des emojis dans presque tous les titres**, et des jeux de mots partout : la marque était chaleureuse mais pas premium.
- **Des pages clonées** : chien, chat et NAC partageaient le même gabarit avec des jeux de mots différents, sans vraie différence pour le lecteur.
- **Des images de travail visibles** en production sur l'accueil.
- **Aucune passerelle vers l'application** : le bouton « Réserver » menait à un formulaire générique, le visiteur devait tout ressaisir.

La refonte a gardé ce qui faisait l'identité (les illustrations, le vocabulaire du « chouchoutage ») et retiré ce qui la desservait.

## Positionnement

| | Plateformes de mise en relation | Pet Cheri |
|---|---|---|
| Choix du prestataire | Le client compare des profils | L'équipe choisit selon l'animal (espèce, âge, santé, comportement) |
| Suivi | Messagerie entre client et prestataire | Une équipe qui suit chaque demande |
| Facturation | Paiement à la réservation | Une note par mois et par client, tous prestataires confondus |
| Expérience | Fonctionnelle | Premium, de la vitrine aux e-mails |

## Les principes qui ont guidé les arbitrages

1. **Une seule marque, trois surfaces.** Le client ne doit pas sentir qu'il change de produit en passant du site à l'application ou à l'application mobile.
2. **L'équipe au centre.** Une conciergerie vit de son équipe : chaque outil admin vise à lui faire gagner du temps sur une tâche répétée (trouver un prestataire, facturer, relancer).
3. **Rien de faux dans les documents.** Une note, un avoir, un e-mail : ce qui part chez le client doit être juste et traçable.
4. **Ne pas promettre ce qu'on ne sait pas mesurer.** Les données importées de l'ancien système sont incomplètes : on instrumente d'abord, on conclut ensuite.
