# Dabali : cahier des écrans pour le prototype Figma

Ce document liste tous les écrans à dessiner. Il sert aux designers (et aux agents) qui produisent les écrans HTML. L'équipe importe ensuite ces écrans dans Figma avec le plugin **html.to.design** et les relie en mode Prototype.

> **Règle du hackathon :** ces fichiers sont des **maquettes de design** destinées à l'import Figma. Ce n'est pas le code de l'application, et rien ne sera réutilisé le jour J.

## 1. Règles communes (obligatoires)

- Chaque écran est un fichier HTML autonome, construit sur le **gabarit** ci-dessous.
- **Styles** : il faut importer `../../tokens.css` puis `../../components.css`, sans aucune couleur en dur dans l'écran. Si un style manque, on l'ajoute dans un `<style>` local, avec des `var(--…)` uniquement.
- **Formats** : téléphone `frame--phone` (390 × 844), tablette `frame--tablet` (1280 × 800), ticket : largeur 384, hauteur libre.
- **Icônes** : uniquement Lucide `<i data-lucide="nom" class="ic"></i>`. **Aucun emoji, nulle part.**
- **Photos de plats** : on utilise un bloc `.photo` / `.dish__photo` / `.tile__photo` avec l'icône du plat et le libellé `photo du plat`. L'équipe y mettra les vraies photos dans Figma. On peut varier le dégradé avec une variable locale.
- **Liens du prototype** : chaque bouton qui mène à un autre écran est un `<a href="…">` vers le fichier cible, avec `data-link="ID-cible"`. Ces liens doivent correspondre à la colonne « Liens » du tableau.
- **Langue** : français, au ton maison. On tutoie au maquis : chaleureux, simple, sans jargon. Les messages d'erreur sont rassurants.
- **Tout le contenu tient dans le cadre**, sans barre de défilement. S'il y a trop de contenu, on coupe proprement le bas de la liste, comme une liste qu'on ferait défiler.
- **Accessibilité** : les cibles tactiles font au moins 48 px, et 64 px en mode sans lecture. Un état n'est jamais indiqué par la couleur seule : il faut toujours une icône ou un libellé en plus.

### Gabarit

```html
<!doctype html>
<html lang="fr"><head><meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>C03 · Menu</title>
<link rel="stylesheet" href="../../tokens.css">
<link rel="stylesheet" href="../../components.css">
</head>
<body class="screen">
  <main class="frame frame--phone" data-screen="C03">
    <div class="statusbar"><span>19:42</span><span class="icons"><i data-lucide="signal" class="ic"></i><i data-lucide="wifi" class="ic"></i><i data-lucide="battery-full" class="ic"></i></span></div>
    <!-- contenu -->
  </main>
  <script src="https://unpkg.com/lucide@0.460.0/dist/umd/lucide.min.js"></script>
  <script>lucide.createIcons();</script>
</body></html>
```

Le logo est dans `../../logo/dabali-logo.svg` et `../../logo/dabali-mark.svg`, à inclure avec `<img>`.

## 2. L'univers (données de démo, à respecter partout)

- **Restaurant :** *Le Baobab*, maquis grillades, Angré 8e tranche, Cocody. Ouvert de 10h30 à minuit.
- **Patronne :** *Tantie Awa* (Awa Koné). Elle lit difficilement et utilise la voix et les images.
- **Serveuse :** *Fanta*. **Caissière :** *Fanta* aussi, en petite équipe.
- **Client héros :** *Yannick* (+225 07 •• •• 21), habitué, plat préféré : alloco poulet + bissap.
- **Amis de Yannick, table 7 :** *Koffi*, *Aïcha*, *Mariam*.
- **Livreurs :** *Moussa K.* (4,9), *Serge A.* (4,6), *Ibrahim T.* (4,8).
- **Menu (FCFA) :**

  | Plat | Prix | Icône |
  |---|---|---|
  | Poisson braisé + attiéké | 5 000 | `fish` |
  | Kédjénou de poulet | 4 500 | `drumstick` |
  | Foutou sauce graine | 3 500 | `soup` |
  | Alloco poulet | 2 500 | `banana` |
  | Garba | 1 000 | `wheat` |
  | Attiéké supplément | 500 | `wheat` |
  | Bissap glacé 50 cl | 500 | `cup-soda` |
  | Gnamakoudji 50 cl | 500 | `cup-soda` |

- **Commande de la table 7 :** 2 poissons, 1 kédjénou, 2 allocos, 1 foutou, 3 bissaps, 1 attiéké supplément, soit un sous-total de 25 000. Avec une remise fidélité de −1 000, le **total TTC est de 24 000 F** (HT 20 339, TVA 18 % 3 661).
- **Répartition de la cotisation :** Koffi 6 000 (Wave, payé), Aïcha 9 000 (Orange Money, payé), Yannick 3 000 (alloco + bissap, Wave), Mariam 6 000 (Wave, lien envoyé). Total : 24 000.
- **Ticket :** N° 000487, 21/11/2026 à 21:18, caisse 01, 4 couverts. Code de contrôle 7F3A-91C2.
- **Journée du 21/11 (rapport Z n° 0142) :** 64 tickets, 118 couverts, total 486 500 F, réparti en espèces 112 000, Wave 241 500, Orange Money 98 000 et MTN MoMo 35 000. Écart de caisse : 0. 2 annulations (−7 500) validées par la patronne.
- **Statistiques (millions F), janvier à octobre :**
  - 2026 : 10,8 · 10,1 · 8,6 · 11,9 · 12,4 · 11,2 · 13,1 · 10,2 · 12,8 · 13,6 (total 114,7)
  - 2025 : 9,2 · 8,7 · 7,9 · 9,6 · 10,1 · 9,8 · 10,4 · 9,5 · 9,9 · 10,6 (total 95,7)
  - Évolution : +19,9 %.
- **Langues proposées :** Français, Dioula, Baoulé, Nouchi.
- **Billets stylisés :** `.bill--10000/5000/2000/1000` et `.coin` (500). On affiche toujours la décomposition exacte du montant.

## 3. Liste des écrans

### Client, téléphone (`ecrans/client/`)

| ID | Fichier | Contenu | Liens |
|---|---|---|---|
| C01 | `C01-bienvenue-nouveau.html` | Accueil d'un 1er passage, en carte chaleureuse : « Akwaba ! C'est ta première fois chez nous ? ». Choix de la langue (4 grands boutons avec haut-parleur). Les 3 plats préférés des clients, avec leur note. Cadeau « Bissap offert pour ta première visite ». | « Voir le menu » → C03 · « Mode images » → C04 |
| C02 | `C02-bienvenue-habitue.html` | « Bonne arrivée Yannick ! Content de te revoir. » Message vocal de Tantie Awa (lecteur 0:06). Carte « Comme d'habitude ? Alloco poulet + bissap, 3 000 F ». Ce soir : plat du jour, match à 20h30, Wi-Fi. Serveuse Fanta, avec un bouton pour l'appeler. | « Oui, comme d'habitude » → C05b · « Voir le menu » → C03 |
| C03 | `C03-menu.html` | En-tête « Table 7 · Le Baobab ». Puces de catégorie. Délai de préparation en direct (« prêt en 12 min »). Liste de plats avec photo, description et prix, avec un bouton + ou un compteur de quantité. Badge « plus que 4 portions » sur le foutou. Barre d'action en bas. | Barre « Voir ma commande · 3 · 12 500 F » → C05 · icône images → C04 |
| C04 | `C04-menu-images.html` | Mode sans lecture : grille 2 × 3 de grandes tuiles photo, chacune avec un haut-parleur et le prix en billets. Compteur visible sur 2 tuiles sélectionnées (poisson et alloco). Langue Dioula active. Barre du bas avec panier en icône et total en billets (5 000 + 2 000 + 500). Aucun texte n'est indispensable. | Valider (panier) → C06 |
| C05 | `C05-panier.html` | Récapitulatif de la commande : lignes modifiables, note libre (« piment ++ »), choix « Sur place / À emporter ». Total. Mention rassurante : « Tu paies à la fin, comme d'habitude ». | « Envoyer en cuisine » → C07 |
| C05b | `C05b-panier-habitude.html` | Variante de C05 pour le parcours « Comme d'habitude » : 1 alloco poulet + 1 bissap = 3 000 F, note « piment à part ». | « Envoyer en cuisine » → C07b |
| C06 | `C06-relecture-vocale.html` | Mode sans lecture : grandes icônes poisson ×1 et alloco ×1 (quantité en points), total en grands billets. Indicateur audio « lecture en dioula ». Phrase entendue en petit. Deux énormes boutons ✕ Changer (rouge) / ✓ C'est bon (vert). Bouton pour appeler la serveuse. | ✓ → C07 · ✕ → C04 |
| C07 | `C07-commande-en-cuisine.html` | « C'est parti en cuisine ! » Suivi en étapes : reçue (coche), en préparation (en cours), prête, servie. Estimation « Fanta t'apporte ça vers 19:58 ». Rappel de ce qui a été commandé. Actions : ajouter quelque chose, appeler Fanta. | « Demander l'addition » → C08 |
| C07b | `C07b-commande-habitude-en-cuisine.html` | Variante de C07 qui rappelle alloco poulet + bissap. | « Demander l'addition » → C08 |
| C08 | `C08-cotisation.html` | « On cotise ? » Total de la table 24 000, barre de progression (15 000 payés). Liste des 4 personnes avec leur statut (payé, à payer, lien envoyé). Choix « Parts égales / Chacun ses plats ». Ma part : 3 000. | « Payer ma part avec Wave · 3 000 F » → C09 |
| C09 | `C09-paiement.html` | Choix du moyen de paiement : Wave (sélectionné), Orange Money, MTN MoMo, Moov, espèces auprès de Fanta. Montant en grand et en billets. Étape de confirmation. Ne pas reproduire les logos des opérateurs : pastilles de couleur et nom en texte seulement. | « Confirmer 3 000 F » → C10 |
| C10 | `C10-paiement-reussi.html` | Succès chaleureux : « Merci Yannick, c'est payé ! ». Mini ticket numérique de sa part. +30 points fidélité. Boutons : voir le ticket complet, laisser un avis vocal, recevoir sur WhatsApp. « Bonne digestion, à la prochaine ! » | « Voir le ticket » → T01 · « Ma fidélité » → C11 · « Sur WhatsApp » → C15 |
| C11 | `C11-fidelite.html` | Carte de points (2 080 points, niveau Habitué, progression vers un poisson offert). Tontine gourmande « Les gars du bureau » (7 200 / 10 000). Anniversaire jeudi, dessert offert. Parrainage par WhatsApp (+300 points chacun). Barre de navigation basse. | « Dernière louche » (tab) → C12 |
| C12 | `C12-derniere-louche.html` | Anti-gaspillage près de toi : liste d'offres d'invendus (prix barré, restant, distance, heure limite). Impact personnel : 7 repas sauvés, 4,2 kg. | aucun (écran de réserve) |
| C13 | `C13-suivi-livraison.html` | Commande #D-0315 livrée à Riviera 2. Carte stylisée en SVG (rues, lagune, restaurant, livreur, client). « Moussa arrive dans 6 min ». Carte du livreur avec bouton d'appel. Étapes horodatées. Code de livraison 4821. | aucun |
| C14 | `C14-whatsapp-commande-vocale.html` | Conversation WhatsApp simulée avec « Le Baobab · Commandes » : note vocale du client et sa transcription, récapitulatif structuré par l'assistant, confirmation, lien de paiement. | aucun |
| C15 | `C15-whatsapp-recu.html` | WhatsApp : ticket de la part de Yannick en image (mini ticket), reçu audio en dioula avec sa transcription, résumé en icônes = billets, liens « Avis vocal » et « Facture PDF ». | aucun |

### Cuisine, tablette (`ecrans/cuisine/`)

| ID | Fichier | Contenu | Liens |
|---|---|---|---|
| K01 | `K01-ecran-cuisine.html` | Fond sombre. En-tête : « Cuisine · Le Baobab », compteurs (8 en cours, 1 en retard), badge « Hors-ligne : synchronisation auto ». Colonnes « À faire / En préparation / Prêt ». Tickets avec source (Salle QR, WhatsApp, Glovo, Yango), minuteur, lignes et notes (« piment ++ »). Bordure verte, jaune ou rouge selon l'urgence, toujours avec un libellé. Grands boutons d'action. | aucun |

### Patron, téléphone (`ecrans/patron-mobile/`)

| ID | Fichier | Contenu | Liens |
|---|---|---|---|
| M01 | `M01-connexion-images.html` | Connexion sans clavier : « Bonjour Tantie Awa ». Code secret en images : grille de 9 images (mangue, poisson, soleil, etc.), 3 choisies avec des points de progression. Option « Me connecter à la voix ». | « Entrer » → P01 |
| M02 | `M02-photo-ardoise.html` | Inscription, étape 2 sur 3 : photo de l'ardoise du maquis (cadre de visée), puis plats détectés par l'IA avec leur prix et un score de confiance (« À vérifier » si inférieur à 85 %). | « Valider mon menu » → M03 |
| M03 | `M03-qr-tables.html` | Inscription, étape 3 sur 3 : « Ton menu est prêt ! ». Aperçu des QR codes des tables 1 à 12 (carte imprimable avec le logo). Bouton pour imprimer ou partager. QR décoratif dessiné en SVG ou en canvas. | « Ouvrir mon tableau de bord » → P01 |
| M04 | `M04-patronne-vocal.html` | Fond sombre. Gros bouton micro. Question posée en dioula, traduite : « Combien j'ai gagné aujourd'hui ? ». Réponse : 486 500 F, en billets (×48 et plus), top 3 des plats en icônes avec barres, flèche de hausse, rappel « réponse lue à voix haute ». | « Voir les détails » → P01 |
| M05 | `M05-alerte-annulation.html` | Notification anti-vol : « Fanta veut annuler 2 bissaps sur le ticket 000476 (−1 000 F). Raison : client parti ». Gros boutons « Refuser / Valider ». Historique des annulations du jour. | « Valider » → P06 |

### Patron, tablette back-office (`ecrans/patron/`)

Navigation latérale commune (`.sidenav`) : Aujourd'hui · Livraisons · Statistiques · Clients & campagnes · Caisse · Recherche & documents. Le logo est en haut, et « Tantie Awa » avec son avatar en bas.

| ID | Fichier | Contenu | Liens (sidenav) |
|---|---|---|---|
| P01 | `P01-aujourdhui.html` | 4 KPI (CA du jour 486 500 F +12 %, 118 couverts, attente moyenne 14 min, gaspillage 3,1 kg). Courbe des ventes de la journée (pics à midi et le soir). Prévision IA pour demain dimanche, avec les raisons (fin de mois, match des Éléphants à 17h, pas de pluie) et les portions par plat. Liste d'achats générée. Alerte anti-gaspi à 21h30 avec « Publier l'offre ». | chaque entrée de navigation → P0x |
| P02 | `P02-livraisons.html` | KPI (5 en cours, 38 livrées, 27 min, 46 500 F en espèces à récupérer). Grande carte SVG de Cocody (Angré, II Plateaux, Riviera 2, Palmeraie, lagune Ébrié) avec livreurs et clients. Liste des livraisons avec statuts (En route, Retard +8 min, En cuisine, Livré). Tableau des livreurs. | idem |
| P03 | `P03-statistiques.html` | Filtres : Semaine / Mois / **Année**, 2026 contre 2025. KPI. Courbe 2026 (orange, trait plein) contre 2025 (`--c-blue`, pointillés), axes et grille discrets, légende, cercles rouges sur les chutes (mars, août). 4 panneaux : Ce qui a marché, Ce qui n'a pas marché, Chutes détectées (hebdo, mois, année), Conseils pour grandir (chiffrés, avec bouton d'action). | idem |
| P04 | `P04-clients-campagnes.html` | 5 segments (Habitués 214, À relancer 86 [sélectionné], Anniversaires 23, Fans du poisson 312, Clients bureau 140). Tableau des clients fidèles. Éditeur de campagne : visuel généré par l'IA, aperçu WhatsApp, canal, date, bouton « Programmer ». Résultats de la dernière campagne (412 envoyés, 371 lus, 58 venus, 436 000 F). Mention du consentement. | idem |
| P05 | `P05-recherche-documents.html` | Grande barre de recherche (« mariam octobre », raccourci Ctrl K, bouton voix). Résultats groupés : Clients, Tickets, Documents. Bibliothèque de documents avec filtres et téléchargement. Mention « Sauvegarde automatique chiffrée ». | idem |
| P06 | `P06-caisse.html` | Caisse du jour : tickets du jour (n°, heure, table ou canal, montant, moyen, statut). Annulations avec qui, pourquoi et validation de la patronne. Répartition par moyen de paiement. Aperçu du rapport Z, avec boutons « Clôturer la journée » et « Imprimer le Z ». | idem · « Imprimer le Z » → T03 |

### Tickets thermiques (`ecrans/tickets/`)

Utiliser `.receipt` à l'intérieur d'un `<main class="frame" style="width:384px;height:auto;background:transparent">`.

| ID | Fichier | Contenu |
|---|---|---|
| T01 | `T01-ticket-client.html` | Ticket de la table 7, complet, comme dans le dossier : en-tête, lignes en majuscules avec icône de plat et « 2 x 5 000 », sous-total, remise, TOTAL TTC, HT, TVA, total en billets (en noir et blanc), cotisation, fidélité, QR, code-barres, code de contrôle, « MERCI, À BIENTÔT ». |
| T02 | `T02-bon-cuisine.html` | Bon de commande imprimé en cuisine : très gros numéro de table, heure, source, lignes en grand avec quantités, notes en inversé (« PIMENT ++ »), « Serveuse : Fanta ». |
| T03 | `T03-rapport-z.html` | Rapport Z de clôture n° 0142, comme dans le dossier. |

## 4. Récit du jury (pour le parcours de présentation)

C'est la journée de Tantie Awa et de Yannick, le samedi 21 novembre :
1. Le matin, Tantie Awa se connecte avec son code en images (M01) et voit sa prévision du jour (P01).
2. Le soir, Yannick arrive au Baobab avec ses amis et scanne le QR de la table : il est accueilli par son prénom (C02).
3. Il commande (C03 → C05) et la commande arrive en cuisine (K01, T02).
4. Une amie qui ne lit pas commande en images (C04 → C06).
5. La table cotise (C08 → C09 → C10) et le ticket sort de l'imprimante (T01).
6. Une serveuse demande une annulation, et la patronne la valide depuis son téléphone (M05 → P06).
7. À 23h, Tantie Awa demande à voix haute ce qu'elle a gagné (M04), puis clôture la caisse (T03).
8. En fin de mois, elle compare 2026 à 2025, voit ses chutes et lance une campagne vers les clients à relancer (P03 → P04).
