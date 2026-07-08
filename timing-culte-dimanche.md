# Spécifications — Page HTML "Timing de Culte Dimanche"

> Fichier de brief à donner à Claude Code pour générer une page HTML unique (`index.html`), fidèle au visuel du document PDF source (Vases d'Honneur — Assemblée Rehoboth Bonoua).

## 1. Objectif

Reproduire fidèlement en HTML/CSS (une seule page, format portrait imprimable, type A4) le document "Timing de culte dimanche — 2e culte", avec :
- Le même contenu texte (aucune donnée inventée)
- La même structure de tableaux
- Le même code couleur
- Un **emplacement réservé pour le logo** (à remplacer plus tard par le vrai logo fourni par l'utilisateur) — utiliser un placeholder simple (ex. un cercle/carré avec le texte "LOGO" ou une balise `<img>` avec `src="logo-placeholder.png"` commentée)

## 2. Palette de couleurs

| Élément | Couleur | Usage |
|---|---|---|
| Bleu foncé | `#1B3A6B` (bleu marine) | Encadré titre "TIMING DE CULTE DIMANCHE" — fond blanc, bordure bleue épaisse, texte bleu |
| Jaune/Or | `#F5B700` ou `#FFC107` | Bordure du bloc titre, fond des étiquettes "LES GOOD NEWS", accents |
| En-tête tableau principal | Fond orange/ambré clair `#F4C542` | En-têtes "HEURES / DUREE / CONTENUS / INTERVENANTS" |
| En-tête tableau Good News | Fond bleu `#2E75B6` avec texte blanc | En-tête "RUBRIQUES / INFORMATIONS" |
| Texte souligné en rouge | `#D93025` | Les mots "Dimanche", "Mercredi des Champions", "Réceptions" dans le bloc CULTES |
| Bordures de tableau | Noir fin `#000000` ou gris foncé | Toutes les cellules |
| Fond général | Blanc | — |

## 3. Structure générale de la page

```
┌─────────────────────────────────────────────┐
│ [LOGO placeholder]   [Bloc titre encadré]    │  <- en-tête
├─────────────────────────────────────────────┤
│ Tableau infos (Date / Groupe / Dirigeant /   │
│ Orateur / Durée) — 2 colonnes, sans bordure  │
│ extérieure visible, libellés en gras         │
├─────────────────────────────────────────────┤
│ Tableau principal du déroulé (5 colonnes     │
│ visuelles : Heures | Durée | Contenus |      │
│ Intervenants) — en-tête fond ambré           │
├─────────────────────────────────────────────┤
│ Bandeau jaune "LES GOOD NEWS" (encadré)      │
├─────────────────────────────────────────────┤
│ Tableau Good News (2 colonnes : Rubriques /  │
│ Informations) — en-tête fond bleu, texte     │
│ blanc                                        │
└─────────────────────────────────────────────┘
```

## 4. Logo (à intégrer plus tard)

- Emplacement : coin supérieur gauche, aligné avec le bloc titre
- Taille approx. : 80–100px de large
- Pour l'instant : placeholder (rectangle gris clair avec texte centré "LOGO" ou balise `<img>` commentée pointant vers `logo.png`)
- Le vrai logo (Vases d'Honneur — cercle avec colombe/flamme, tampon circulaire "ASSEMBLÉE REHOBOTH BONOUA") sera fourni séparément

## 5. En-tête — Bloc titre

- Encadré rectangulaire, bordure bleu marine épaisse (~3px), fond blanc
- Texte centré, en majuscules, gras, bleu marine
- Contenu exact : **"TIMING DE CULTE DIMANCHE  2e CULTE"**
  - Note : le "e" de "2e" doit être en exposant (`<sup>`)

## 6. Tableau infos générales

Deux colonnes, pas de quadrillage visible (ou très léger), libellé à gauche en gras :

| Libellé | Valeur |
|---|---|
| Date | Dimanche 05 Avril 2026 |
| Groupe de louange | HEAVEN PRAISE |
| Dirigeant | M. SIDIO |
| Orateur | Pasteur Honorat KPAZARA |
| Durée | **01h45min** (en gras) |

## 7. Tableau principal — Déroulé du culte

En-tête sur fond ambré/orange clair, texte noir gras, centré. Colonnes : **HEURES | DUREE | CONTENUS | INTERVENANTS**

| HEURES | DUREE | CONTENUS | INTERVENANTS |
|---|---|---|---|
| 10h00-10H03 | 03 mn | PROCLAMATION | Com |
| 10h03-10h13 | 10 mn | Adoration | Heaven Praise / Com |
| 10h13-10h18 | 05 mn | Bienvenue, prière et 1ère offrande | Dirigeant/portier/ Heaven Praise / Com |
| 10h18-10h30 | 12 mn | Adoration ou louange | Heaven Praise / Com |
| 10h30-10h36 | 06 mn | ECODIM | ECODIM/ Com |
| 10h36-11h26 | 50 mn | Message de l'orateur | Pasteur /Com |
| 11h26-11h31 | 05 mn | 2è offrandes | Pasteur/portier/ Heaven Praise |
| 11h31-11h36 | 05 mn | Sainte Cène | Pasteur/ Heaven Praise / Com /Sainte cène |
| 11h36-11h40 | 04 mn | Good news | Pasteur ou AP / Com |
| 11h40-11h43 | 03 mn | Présentation des nouvelles personnes | Pasteur/ADN/ Com |
| 11h43-11h45 | 02 mn | Prière finale | Pasteur ou AP/ Com |

Puis une ligne finale fusionnée sur toute la largeur (fond neutre, texte gras centré) :

**11h45MN — FIN DU CULTE DE LA VIE**

Notes de mise en forme :
- Colonnes "HEURES" et "DUREE" : texte centré
- Colonne "CONTENUS" : gras
- Bordures noires fines sur toutes les cellules

## 8. Bandeau "LES GOOD NEWS"

- Encadré rectangulaire, bordure jaune/or, fond blanc ou jaune très clair
- Texte centré, gras, majuscules, couleur bleu marine ou noir
- Placé entre le tableau principal et le tableau Good News

## 9. Tableau Good News

En-tête sur fond bleu (`#2E75B6`), texte blanc, gras. Deux colonnes : **RUBRIQUES | INFORMATIONS**

**Ligne "VIDEOS"** (liste à puces dans la cellule Informations) :
- Le Boost
- C'Pentécote 2026

**Ligne "PLANCHES"** (liste numérotée) :
1. Galilée Célébration le lundi 6 avril à la plage de Port-Bouët (Gonzagueville) à partir de 9h. (Transport : 1600f)
2. GRAND CINÉMA ce samedi 11 avril à partir de 14 heures à VH Assemblée Rehoboth
3. Culte Bloom le Dimanche 26 Avril à 13 heures.
4. Présentation du bébé du couple Ouattara 12 Avril 2026 au 2e culte
5. Rencontre des Kanegnons ce dimanche 05 Avril après le 2e culte

**Ligne "CULTES"** (liste numérotée, avec certains mots en rouge/souligné) :
1. <span style="color:red">Dimanche:</span> 1er Culte: 08h00-09h45 & 2e Culte: 10h00-11h45
2. <span style="color:red">Mercredi des Champions</span> : 18h30-20h30
3. <span style="color:red">Réceptions</span> : Mardi et Jeudi de 9h à 15h au temple REHOBOTH

**Ligne "ADN"** (champs à remplir à la main — utiliser des lignes pointillées) :
- A Droite : ..........................................................
- A Gauche : ..........................................................

## 10. Typographie

- Police sans-serif propre (ex. `Arial`, `Helvetica`, ou `'Segoe UI', sans-serif`)
- Titres/en-têtes : gras, légèrement plus grands
- Corps de texte : taille lisible (~11–12px à l'écran, adapté à l'impression A4)

## 11. Contraintes techniques

- Un seul fichier HTML autonome (CSS inline dans une balise `<style>`, pas de dépendances externes sauf polices Google Fonts si besoin)
- Doit bien s'imprimer en A4 portrait (prévoir une règle `@media print`)
- Responsive minimal (le document reste principalement un visuel de type "flyer imprimable")
- Pas de JavaScript nécessaire (page statique)
- Prévoir des classes CSS claires et commentées pour faciliter le remplacement du logo plus tard (`.logo-placeholder`)

## 12. Prochaine étape

Une fois cette page générée, le logo réel (Vases d'Honneur) sera fourni pour remplacer le placeholder dans `.logo-placeholder`.
