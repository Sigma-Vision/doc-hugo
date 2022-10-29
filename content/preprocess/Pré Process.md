---
title: "Traitement de l'Image"
date: 2022-09-25T13:37:31+02:00
draft: false
---

# GrayScale

Le grayscale a pour but de transformer l'image en nuance de gris.

Pour cela nous utilisons la recommandation 601 pour les couleurs non linéaires de la Commission Internationnale de l éclairage. En effet cette recommandation est avec la correction du gamma.
Voici donc la formule : `Gris = 0.299 * Rouge + 0.587 * Vert + 0.114 * Bleu`

ensuite l'image est binarisée avec une binarisation d'Otsu

# Binarisation d'Otsu

# Detection de la grille

Il faut enfin detecter la grille et les cellules du soddoku. Pour cela il est nécessaire de dilatter la grille. En effet, la binarisation a pour effet de créer des pixels maquants : des trous. Ces derniers empèchent une bonne reconnaissance de la grille.

## Dilatation

## Detection de la grille

Pour detecter la grille nous utilisons une sorte `Labelling connected components`.
Pour résumer, un label va être attribué à tout les groupes de pixels existants. Nous créons donc une grille de la même taille que nous remplissons avec ses valeurs. Ensuite il faut repasser sur la grille pour verifier que deux labels differents ne se touchent pas.

Ensuite il faut trouver le label le plus utilisé pour ne garder que lui, et remplacer les autres par la couleur du background. Comme par magie si l'on affiche l'image du suddoku, il ne reste plus que lui !