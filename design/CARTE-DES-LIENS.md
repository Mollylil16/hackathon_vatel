# Carte des liens du prototype Figma

Ce document est pour la personne qui relie les écrans en mode Prototype dans Figma.
Il est généré à partir des liens présents dans les écrans HTML, il est donc identique à ce qui est cliquable dans Chrome.

**Réglages pour chaque lien :** déclencheur *On tap* · action *Navigate to* · animation *Smart animate* 250 ms *Ease out*. Entre deux appareils différents (téléphone vers tablette), utilisez *Dissolve*.

**Points de départ (Flow starting points) :** C02 (parcours client), C04 (sans lecture), M01 (patronne).

## Liens écran par écran

| Écran de départ | Bouton à sélectionner | Écran d'arrivée |
|---|---|---|
| C01 | Voir le menu | C03 |
| C01 | Mode images | C04 |
| C02 | Oui, comme d'habitude | C05b |
| C02 | Voir le menu | C03 |
| C03 | Icône « Mode images » en haut à droite | C04 |
| C03 | 3 Voir ma commande 12 500 F | C05 |
| C04 | Gros bouton vert de validation, à côté du panier | C06 |
| C05 | Envoyer en cuisine 12 500 F | C07 |
| C05b | Envoyer en cuisine 3 000 F | C07b |
| C06 | Changer | C04 |
| C06 | C'est bon | C07 |
| C07 | Demander l'addition | C08 |
| C07b | Demander l'addition | C08 |
| C08 | Payer ma part avec Wave 3 000 F | C09 |
| C09 | Confirmer 3 000 F | C10 |
| C10 | +30 points fidélité Tu as maintenant 2 080 points Ma fidélité | C11 |
| C10 | Voir le ticket complet | T01 |
| C10 | Recevoir sur WhatsApp | C15 |
| C11 | Dernière louche | C12 |
| M01 | Entrer | P01 |
| M02 | Valider mon menu | M03 |
| M03 | Ouvrir mon tableau de bord | P01 |
| M04 | Voir les détails | P01 |
| M05 | Valider | P06 |
| P01 | 5 livraisons | P02 |
| P03 | Lancer | P04 |
| P06 | Imprimer le Z | T03 |

## Navigation latérale du back-office (P01 à P06)

Sur chaque écran P0x, chaque entrée du menu de gauche mène à l'écran correspondant :

| Entrée du menu | Écran |
|---|---|
| Aujourd'hui | P01 |
| Livraisons | P02 |
| Statistiques | P03 |
| Clients & campagnes | P04 |
| Caisse | P06 |
| Recherche & documents | P05 |

Astuce Figma : créez la navigation comme un composant avec un lien par entrée. Il suffit alors de faire les liens une seule fois.
