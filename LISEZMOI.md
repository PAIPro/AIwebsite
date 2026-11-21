# Modèle de portfolio

Page unique (`index.html`) issue de la maquette A, vidée de tout contenu personnel. Elle garde la structure, la nav, la fusée de progression, les trois langues (FR, EN, JA) et le logo animé.

## Fichiers

| Fichier | Rôle |
|---|---|
| `index.html` | la page, avec ses trois langues dans des `<template>` (`tpl-fr`, `tpl-en`, `tpl-ja`) |
| `base.css` | tokens (couleurs, polices, courbes) et composants communs |
| `logo-ai.css` | géométrie et animation du logo |
| `favicon.svg`, `favicon.ico`, `apple-touch-icon.png` | icônes |
| `bg.jpg`, `blueprint.png` | photo du hero, trame de fond des sections |

## À remplacer

Cherchez ces textes de substitution, dans la page affichée **et** dans les trois `<template>` :

- `Votre texte ici.`, `Your text here.`, `ここに文章を入れます。` : textes de contenu ;
- `Libellé`, `Label`, `ラベル` : titres courts et libellés ;
- `Tag`, `タグ` : compétences et technologies ;
- `Bloc`, `Block`, `ブロック` : étiquettes des deux schémas de projets ;
- les chiffres mis à `0` : années, périodes, chiffres clés ;
- `PRÉNOM · NOM`, `Prénom Nom`, `名前`, `苗字` : identité (nav, pied de page, titre de la page) ;
- `contact@exemple.com` : adresse des boutons « Écrire un e-mail ».

## Logo

Le logo garde sa forme : un cadre, une première initiale (le **A**, dessinée en SVG dans `.ai-a`) et une barre inclinée pour la seconde (le **I**, `.ai-i`). Les bandes affichent `Prénom` et `Nom`. Pour l'adapter :

1. mettez le reste du prénom et du nom dans les bandes `.ai-band-1` et `.ai-band-2` ;
2. redessinez la lettre `.ai-a` si votre initiale n'est pas un A, et changez la barre si la seconde n'est pas un I ;
3. réglez la largeur des bandes (`--b1`, `--b2`) et la largeur totale (`--ai-span`) dans `logo-ai.css` ;
4. la couleur suit `--accent` (dans `base.css`).

Le favicon reprend le logo replié. Si vous changez les lettres ou la couleur, modifiez `favicon.svg`, puis régénérez les deux images, par exemple avec ImageMagick :

```sh
magick -background none -density 600 favicon.svg -resize 180x180 apple-touch-icon.png
magick -background none -density 600 favicon.svg -define icon:auto-resize=48,32,16 favicon.ico
```

## Options d'URL

- `?still` : page figée, sans animation ;
- `?lang=fr|en|ja` : langue à l'ouverture (sinon la dernière choisie).

L'ouverture se joue à chaque chargement et à chaque changement de langue : le logo d'abord, centré, puis le reste de la page. Avec le mouvement réduit, tout s'affiche directement.
