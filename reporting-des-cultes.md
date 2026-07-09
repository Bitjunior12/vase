# Spécifications — Page HTML "Reporting des Cultes"

> Fichier de brief à donner à Claude Code pour générer une page HTML unique (`index.html`), fidèle au visuel du modèle "Reporting des cultes" (Vases d'Honneur — Assemblée Rehoboth Bonoua). C'est un formulaire imprimable/remplissable, format portrait A4.

## 1. Objectif

Reproduire fidèlement en HTML/CSS (une seule page, format portrait A4) le gabarit "Reporting des cultes", avec :
- Structure en cartes/blocs arrondis avec bordures fines
- Icônes rondes (fond vert foncé, icône blanche) devant chaque section
- Champs à remplir : soit des lignes pointillées, soit des espaces vides pour écriture manuelle (le document est un template vierge, sauf quelques valeurs pré-remplies comme "08h00", "Heaven Praise", "00", et le commentaire "Dans l'ensemble les deux cultes se sont bien déroulés.")
- Un **cadre général englobant toute la page** avec bordure noire épaisse (style "fiche" / "poster")
- Un **emplacement réservé pour le logo** en haut à gauche (à remplacer plus tard par le vrai logo "Vases d'Honneur" fourni par l'utilisateur) — utiliser un placeholder simple

## 2. Palette de couleurs

| Élément | Couleur | Usage |
|---|---|---|
| Vert foncé | `#1B4332` (vert sapin/bouteille) | Titres de sections (bandeaux), cercles d'icônes, texte "REPORTING", cadre "du __/__/2026" |
| Or / jaune doré | `#C9A227` ou `#D4AF37` | Sous-titre "des cultes" (script cursif), trait décoratif courbe en haut, liseré du logo |
| Rouge/bordeaux | `#8B1E1E` ou `#C0392B` | Valeurs chiffrées importantes ("08h00", "T :", "00"), petit trait sous le logo |
| Orange/ambré | `#D68A2D` ou `#E0A030` | Libellés de sous-sections en orange ("THÈME :", "TEXTES BIBLIQUES :", "ORATEUR :", "RÉSUMÉ :", "1er CULTE", "2e CULTE", "DIRIGEANTS :", "GROUPE MUSICAL :", "DÉNOMBREMENT SERVITEURS :") |
| Noir | `#000000` | Texte standard, bordures de cadre général, lignes pointillées |
| Blanc | `#FFFFFF` | Fond général, texte dans les bandeaux verts, icônes |
| Gris clair | `#E5E5E5` ou similaire | Lignes de séparation internes dans certains blocs |

## 3. Structure générale de la page (haut → bas)

```
┌───────────────────────────────────────────────────────────┐
│ [Cadre extérieur noir épais, coins légèrement arrondis]    │
│                                                             │
│  [LOGO placeholder]        REPORTING                       │
│                             des cultes (script doré)        │
│                             [bandeau vert] du __/__/2026    │
│  ──────────────────────────────────────────────────────    │
│  ┌─────────────┐   ┌─────────────────────────────────┐    │
│  │  HEURES     │   │ DÉNOMBREMENT PEUPLE              │    │
│  │  (icône     │   │ PRÉSENCE TOTALE :                │    │
│  │  horloge)   │   │ [tableau 1er culte | 2e culte]   │    │
│  └─────────────┘   └─────────────────────────────────┘    │
│  ┌─────────────────────┐                                   │
│  │ DÉCOMPTE VISITEURS   │                                   │
│  │ ADN** Cumul           │                                   │
│  └─────────────────────┘                                   │
│  ┌─────────────┐   ┌─────────────────────────────────┐    │
│  │ THÈME       │   │ 1er CULTE (voitures/motos)       │    │
│  │ TEXTES BIB. │   │ 2e CULTE (voitures/motos)        │    │
│  │ ORATEUR     │   │ DIRIGEANTS                       │    │
│  │ RÉSUMÉ      │   │ GROUPE MUSICAL                   │    │
│  │             │   │ DÉNOMBREMENT SERVITEURS          │    │
│  └─────────────┘   └─────────────────────────────────┘    │
│  ┌─────────────────────────────────────────────────────┐  │
│  │ REMARQUES (bandeau vert)                             │  │
│  │ ✔ ASPECTS POSITIFS :        ✘ ASPECTS NÉGATIFS :     │  │
│  └─────────────────────────────────────────────────────┘  │
└───────────────────────────────────────────────────────────┘
```

Layout en 2 colonnes principales (colonne gauche / colonne droite) sur la majorité de la page, avec un bandeau "REMARQUES" en pleine largeur tout en bas.

## 4. En-tête

### 4.1 Logo (placeholder, à intégrer plus tard)
- Emplacement : coin supérieur gauche
- Taille approx. : 220–260px de large
- Placeholder simple : rectangle avec texte centré "LOGO" ou balise `<img>` commentée (`<!-- <img src="logo.png" class="logo"> -->`)
- Un petit trait rouge/bordeaux horizontal apparaît sous le logo dans l'original — le reproduire comme simple élément décoratif indépendant du logo

### 4.2 Trait décoratif doré
- Une courbe/diagonale dorée épaisse part du coin supérieur droit de la zone logo et descend vers le bas, façon "swoosh"
- Peut être réalisée en SVG (path courbe) ou en CSS (bordure diagonale / pseudo-élément avec `border-radius` et `transform`)

### 4.3 Titre principal
- "REPORTING" : très grand, gras, majuscules, vert foncé, police à empattements marqués/condensée (style affiche)
- "des cultes" : en dessous, police script/cursive dorée, taille moyenne
- Sous ces deux lignes : un bandeau arrondi fond vert foncé, texte blanc centré, gras : **"du ____/____/ 2026"** (avec deux espaces à remplir pour jour/mois)

## 5. Bloc "HEURES" (colonne gauche, sous l'en-tête)

- Carte à bordure fine arrondie
- Bandeau interne fond vert foncé, texte blanc, gras, centré : **"HEURES"**
- Icône ronde (fond vert foncé, icône horloge blanche) à gauche
- Contenu :
  - "1er culte" (gras, noir) ........... "08h00" (gras, rouge/bordeaux) ........... "-" (tiret, rouge)
  - "2e culte" (gras, noir) ........... "-" (rouge) ........... "-" (rouge)
- Les deux colonnes de valeurs à droite du libellé représentent probablement "heure de début" / "heure de fin"

## 6. Bloc "DÉCOMPTE DES VISITEURS ADN** Cumul" (colonne gauche)

- Bandeau fond vert foncé pleine largeur, texte blanc gras : **"DÉCOMPTE DES VISITEURS ADN** Cumul"** — le mot "Cumul" peut être en orange/doré pour contraste
- Icône ronde (groupe de personnes, blanc sur fond vert) à gauche
- Contenu :
  - "visiteurs : ________________________" (ligne à remplir)
  - "Décision de conversion : **00**" (valeur en rouge/bordeaux, pré-remplie à 00)

## 7. Bloc "DÉNOMBREMENT PEUPLE" (colonne droite, haut)

- Bandeau fond vert foncé pleine largeur du bloc, texte blanc gras centré : **"DÉNOMBREMENT PEUPLE"**
- Sous-titre centré, orange/doré : **"PRÉSENCE TOTALE :"**
- Deux mini-tableaux côte à côte : **"1er culte"** et **"2e culte"**, chacun avec en-tête fond vert foncé/texte blanc, puis lignes :
  - H : ____
  - F : ____
  - E : ____
  - T : ____ (le "T" et sa valeur en rouge — total)
- Chaque mini-tableau a des bordures fines, lignes horizontales de séparation

## 8. Section gauche — Contenu du culte (4 sous-blocs dans une seule carte)

Une grande carte à bordure fine, divisée en 4 sous-sections par des lignes horizontales fines, chacune précédée d'une icône ronde verte à gauche :

1. **THÈME :** (icône livre ouvert) — une ligne pointillée à remplir
2. **TEXTES BIBLIQUES :** (icône bible/croix) — deux lignes pointillées à remplir
3. **ORATEUR :** (icône pupitre/personne) — une ligne pointillée à remplir
4. **RÉSUMÉ :** (icône feuille/stylo) — six lignes pointillées à remplir (bloc plus grand, prend le reste de l'espace vertical de la colonne gauche)

Tous les libellés ("THÈME", "TEXTES BIBLIQUES", "ORATEUR", "RÉSUMÉ") sont en orange/doré, gras, majuscules, suivis de ":"

## 9. Section droite — Logistique (5 sous-blocs, cartes séparées)

### 9.1 Carte "1er CULTE" + "2e CULTE" (véhicules)
- Icône ronde voiture (verte) pour chaque sous-bloc
- **1er CULTE** (orange, gras) :
  - Voitures : ______________
  - Motos : ______________
- Ligne pointillée de séparation
- **2e CULTE** (orange, gras) :
  - Voitures : ______________
  - Motos : ______________

### 9.2 Carte "DIRIGEANTS :"
- Icône ronde (groupe de personnes)
- Libellé "DIRIGEANTS :" en orange, gras
- 1er Culte : ________________________
- 2e Culte : ________________________

### 9.3 Carte "GROUPE MUSICAL :"
- Icône ronde (note de musique)
- Libellé "GROUPE MUSICAL :" en orange, gras, suivi de la valeur pré-remplie **"Heaven Praise"** (texte normal, noir)

### 9.4 Carte "DÉNOMBREMENT SERVITEURS :"
- Icône ronde (groupe de personnes)
- Libellé en orange, gras
- Mini-tableau à 2 colonnes ("1er Culte" / "2e Culte"), en-tête fond vert foncé texte blanc, lignes H / F / T (T en rouge), même structure que le bloc "DÉNOMBREMENT PEUPLE" mais sans ligne "E"

## 10. Bandeau "REMARQUES" (pleine largeur, bas de page)

- Bandeau fond vert foncé pleine largeur, texte blanc, gras, centré : **"REMARQUES"**
- En dessous, carte divisée en 2 colonnes par une ligne verticale fine :
  - **Colonne gauche :** icône ronde verte avec coche blanche (✔) + libellé noir gras **"ASPECTS POSITIFS :"**, puis le texte pré-rempli *"Dans l'ensemble les deux cultes se sont bien déroulés."*, suivi de 2-3 lignes pointillées vides
  - **Colonne droite :** icône ronde rouge avec croix blanche (✘) + libellé noir gras **"ASPECTS NÉGATIFS :"**, suivi de 2-3 lignes pointillées vides (rien de pré-rempli)

## 11. Icônes

Utiliser soit :
- Des SVG inline simples (formes géométriques basiques : horloge, personnes, livre, croix/bible, pupitre, feuille+stylo, voiture, note de musique, coche, croix)
- Ou une police d'icônes déjà présente en CDN autorisé (ex. via `https://cdnjs.cloudflare.com` — Font Awesome libre ou Lucide via CDN si simple à charger)

Toutes les icônes sont blanches sur un cercle plein de couleur (vert foncé pour la plupart, rouge pour la croix "aspects négatifs", vert pour la coche "aspects positifs").

## 12. Typographie

- Titre "REPORTING" : police display/condensée gras à empattements marqués (ex. `'Oswald', 'Anton', sans-serif` via Google Fonts, ou fallback `Arial Black`)
- "des cultes" : police script/cursive (ex. `'Dancing Script', 'Pacifico', cursive` via Google Fonts)
- Corps de texte général : sans-serif classique (`Arial, Helvetica, sans-serif`)
- Libellés de sections : gras, légèrement majuscules

## 13. Contraintes techniques

- Un seul fichier HTML autonome (CSS inline dans `<style>`)
- Polices Google Fonts autorisées via `<link>` (connexion internet requise) — prévoir un fallback système si indisponible
- Doit bien s'imprimer en A4 portrait (prévoir `@media print`)
- Pas de JavaScript nécessaire (page statique, formulaire visuel non interactif — sauf si l'utilisateur souhaite plus tard des champs `<input>` réellement remplissables à l'écran)
- Cadre extérieur noir épais englobant toute la page (comme un poster/fiche)
- Prévoir une classe CSS claire et commentée pour le logo (`.logo-placeholder`) afin de faciliter son remplacement futur

## 14. Prochaine étape

Une fois cette page générée, le logo réel "Vases d'Honneur" sera fourni pour remplacer le placeholder dans `.logo-placeholder`.
