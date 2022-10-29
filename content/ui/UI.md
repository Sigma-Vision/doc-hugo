---
title: "Interface Utilisateur"
date: 2022-09-25T13:37:23+02:00
draft: false
---

L'interface utilisateur sera ce qui sera présenté a l'utilisateur lors de l'execution du programe.
Cette dernière est actuellement divisé en 3 menu différents:
- **Le menu principal** est le menu qui pilote tout les autres menus. Sur ce dernier, nous pouvons loader une image grâce au bouton a droite. Cette dernière sera resize pour l'affichage de facon a ce qu'elle rentre dans l'emplacement qui lui est dédié et apparaitera a gauche. Il y a aussi différents autres boutons qui permetterons d'acceder aux différents autres menus.
- **Le menu d'entrainement du réseau de neurone** est le menu qui sert a entrainer le réseau de neurone du projet avec des images que l'on pourra charger grâçe au bouton Load Image. 
- **Le menu résultat** est le menu qui apparaitra lorsque le programe aura fini de traiter l'image ,ou le pdf résultant du process sera présenté a l'utilisateur. Sur ce dernier, il peut choisir de sauvegarder l'image du sudoku résolu a l'endroit ou il veut.

Pour réaliser cette interface, nous avons utilisé GTK et le logiciel Glade. GTK est une librairie du c permettant la réalisation du back de l'ui et glade un logiciel permettant la réalisation du front de l'ui.

Le tout est compilé avec le compilateur GCC:
```
gcc -Wall -g -mwindows -O2 main.c OCR.exe `pkg-config --cflags --libs gtk+-3.0`
```
