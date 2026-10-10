# Facturation et comptabilité

## Le point de départ

La facturation était le chantier le moins visible et le plus risqué : références en double, régularisations faites hors de l'outil, notes retouchées après envoi. Le code n'était pas toujours en cause. Souvent, la règle comptable n'avait jamais été écrite.

J'ai donc commencé par un cahier des règles, rédigé avec la comptabilité, avant de toucher à un écran.

## Les règles, traduites en produit

| Règle comptable | Ce que fait l'outil |
|---|---|
| Une facturation se rattache à la période du **début de sa première prestation** | Les statistiques et le journal des ventes rangent chaque note à cette date ; un avoir compte à sa propre date |
| Un encaissement compte à **sa** date, quelle que soit celle de la note | Les tableaux de bord séparent facturé et encaissé |
| Le retard de paiement = date d'encaissement moins date d'émission | Calculé et suivi, avec un indicateur « clients à relancer » |
| Une note émise **ne s'annule pas et ne se modifie plus** | Seuls le commentaire interne, le pourboire, l'arrondi et l'avancée du statut restent possibles |
| Toute baisse passe par un **avoir**, toute hausse par une **facture complémentaire** | Les deux citent la note d'origine ; la chaîne d'une note se lit d'un coup d'oeil |
| Un numéro définitif ne se perd pas | Une note naît avec une référence provisoire et ne tire son numéro définitif qu'à l'émission : une note abandonnée ne crée pas de trou dans la numérotation |

## Les cas qui reviennent

Les corrections ne sont pas des exceptions : un créneau ajouté en cours de mois, des dates de garde changées, une régularisation arrivée après l'envoi. Pour chacun, l'outil calcule **l'écart** et prépare le bon document (avoir ou complément « à valider »), dans la langue du client, avec la commission des seules lignes concernées. Jamais une seconde note complète.

Une note émise trop fausse pour être corrigée ligne à ligne se **recalcule depuis la demande** : si elle n'a reçu aucun règlement, elle est annulée par avoir et refaite ; sinon, seul l'écart est émis.

## Une note par client et par mois

Avant, un client suivi par trois prestataires dans le mois recevait trois notes. Aujourd'hui, un panier mensuel par client regroupe toutes ses demandes et tous ses prestataires en **une seule note**. L'équipe la déclenche quand tous les prestataires du mois ont transmis leur relevé ; un batch rattrape les mois restés sans note.

J'ai écarté l'idée d'un nouveau statut de proposition (« à facturer en fin de mois ») : il aurait touché chaque écran du parcours pour un besoin qui ne concernait que la facturation.

## La facture de commission

Pet Cheri facture au client le tarif du prestataire et sa propre commission. La facture de commission est un **document figé**, numéroté dans son propre registre, émis dès que la note l'est, « à l'instant t » : un règlement reçu ensuite n'y figure pas, l'écart ressort en contrôle dans le journal des ventes. Elle n'est jamais recalculée après émission.

## Ce que reçoit l'expert-comptable

- **Un journal des ventes** au format Excel : écritures en partie double, pièces, comptes, et une feuille de contrôles qui signale ce qui ne tombe pas juste.
- **Des tableaux de bord** par société et comparés à l'année précédente : financier, opérations, exploitation, balance âgée, indicateurs.
- **Un historique pluriannuel** qui reprend l'ancien classeur de suivi pour les années d'avant la plateforme.

## Les garde-fous

- Un client ou un prestataire ne lit que ses propres notes.
- Un client n'enregistre un règlement que sur la foi d'une session de paiement Stripe payée pour cette note.
- Les calculs financiers, les avoirs, les compléments et le verrouillage des notes émises sont couverts par des tests unitaires.
- Des tutoriels Notion et vidéo expliquent chaque étape à l'équipe (brouillon, validation, envoi, correction, commission, automatismes, tableaux de bord).
