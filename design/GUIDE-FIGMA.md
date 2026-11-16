# Importer les écrans Dabali dans Figma et faire le prototype cliquable

Ce guide est pour la personne de l'équipe qui monte le prototype Figma.

## Ce que contient le dossier `design/`

| Élément | Rôle |
|---|---|
| `tokens.css`, `components.css` | Le design system : couleurs, typos, composants |
| `design-system.html` | La page de référence du design system, à importer comme page Figma « Design system » |
| `logo/` | Le logo complet et la marque seule, en SVG |
| `ecrans/client/` | 17 écrans téléphone du client (C01 à C15, plus les variantes C05b et C07b du parcours « Comme d'habitude ») |
| `index.html` | La galerie de tous les écrans, à ouvrir en premier |
| `ecrans/cuisine/` | L'écran cuisine sur tablette (K01) |
| `ecrans/patron-mobile/` | 5 écrans téléphone de la patronne (M01 à M05) |
| `ecrans/patron/` | 6 écrans tablette du back-office (P01 à P06) |
| `ecrans/tickets/` | 3 tickets thermiques (T01 à T03) |
| `CARTE-DES-LIENS.md` | Quel bouton mène à quel écran |
| `PARCOURS-JURY.md` | L'ordre de présentation au jury |

Chaque écran s'ouvre directement dans Chrome : double-clic sur le fichier `.html`. Les boutons sont déjà cliquables entre les fichiers, ce qui permet de tester le parcours avant même Figma.

## Étape 1 : préparer Figma (10 min)

1. Créez un fichier Figma nommé **Dabali · Prototype jury**.
2. Créez 4 pages : `Design system`, `Client`, `Cuisine & Patron`, `Tickets`.
3. Les polices viennent de Google Fonts, donc Figma les a déjà : **Bricolage Grotesque**, **Figtree**, **JetBrains Mono** et **Courier Prime**. Avec l'appli Figma de bureau, vérifiez qu'elles s'affichent bien après l'import.

## Étape 2 : importer les écrans avec html.to.design (environ 1 h)

1. Dans Chrome, installez l'extension **html.to.design** (Chrome Web Store), puis le plugin **html.to.design** dans Figma.
2. Dans les réglages de l'extension Chrome (`chrome://extensions` → html.to.design → Détails), activez **« Autoriser l'accès aux URL de fichier »**. Sans ça, elle ne voit pas les fichiers locaux.
3. Ouvrez un écran dans Chrome, par exemple `ecrans/client/C01-bienvenue-nouveau.html`.
4. Cliquez sur l'extension, choisissez le format **Mobile 390** pour un téléphone, **Desktop 1280** pour une tablette ou la largeur adaptée pour un ticket, puis lancez la capture. L'extension produit un fichier `.h2d`.
5. Dans Figma, ouvrez le plugin html.to.design et importez le fichier `.h2d`. Vous obtenez des calques modifiables.
6. Dans chaque import, **ne gardez que le cadre `main.frame`**. Supprimez le fond gris qui entoure l'écran, puis renommez la frame avec l'ID de l'écran (`C01 · Bienvenue nouveau`).
7. Recommencez pour chaque écran.

> **Limites du plan gratuit :** le plan gratuit de html.to.design limite le nombre d'imports. Vérifiez la limite actuelle avant de commencer. Si elle est trop basse, importez d'abord les écrans du parcours jury (voir `PARCOURS-JURY.md`), ou répartissez les imports entre plusieurs comptes de l'équipe.

**Rangement conseillé** : une ligne par parcours.
- Client : C01 → C10 sur une ligne, C11 → C15 en dessous.
- Patron : M01 → M05, puis P01 → P06.

## Étape 3 : remplacer les photos de plats (30 min)

Les blocs « photo du plat » sont des emplacements prévus pour les photos. Prenez de vraies photos des plats, au mieux dans un vrai maquis, sinon des photos libres de droits. Dans Figma, sélectionnez le bloc puis **Fill → Image**. Gardez le même cadrage pour toutes les photos.

## Étape 4 : relier les écrans (environ 1 h)

1. Passez en mode **Prototype**, en haut à droite de Figma.
2. Pour chaque ligne de `CARTE-DES-LIENS.md`, sélectionnez le bouton dans l'écran de départ et tirez le lien vers l'écran d'arrivée :
   - **Déclencheur** : *On tap* (au toucher) ;
   - **Action** : *Navigate to* (aller à) ;
   - **Animation** : *Smart animate*, 250 ms, *Ease out*, entre deux écrans du même appareil, et *Dissolve* entre deux appareils.
3. Choisissez les points de départ des parcours (*Flow starting point*) :
   - **Parcours client** : C02 ;
   - **Parcours sans lecture** : C04 ;
   - **Parcours patronne** : M01.
4. Réglez le modèle d'appareil : *iPhone 14* pour les téléphones et *Presentation* pour les tablettes.

## Étape 5 : répéter la présentation

Lancez le mode **Present** (▶) et suivez `PARCOURS-JURY.md`. Chronométrez-vous : la démo doit tenir en 3 minutes.

## Si quelque chose ne va pas

| Problème | Solution |
|---|---|
| Les icônes sont absentes de la capture | Attendez 2 secondes après l'ouverture de la page avant de capturer : les icônes se chargent par internet. |
| Une police est remplacée | Installez la police sur le PC depuis Google Fonts, puis réimportez. |
| Le ticket est coupé | Choisissez une largeur de capture de 430 px et une hauteur automatique. |
| Les bords dentelés du ticket sont perdus | C'est normal, Figma ne gère pas ce type de masque. Redessinez le bord avec une forme en zigzag, ou gardez un bord droit. |
