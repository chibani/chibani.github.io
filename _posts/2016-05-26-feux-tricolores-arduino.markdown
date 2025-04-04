---
layout: post
title:  "Feux tricolores avec un arduino"
date:   2016-05-27 08:42:00 +0200
categories: bricolage
thumbnail: /assets/posts/redlights/car_with_lights.jpg
intro : >#
  Présentation d'un système de mini-feux tricolores que j'ai construit pour mes enfants.
  Cet article est également un tuto permettant de construire le même système.

---
J'ai récemment fabriqué un ensemble de feux tricolores miniatures pour mes enfants.
Le système est assez simple, composé de 2 paires de feux, comprenant chacun 3 LEDs (vert, jaune, rouge).
{% include youtubePlayer.html id="ZujOyZ-2kiU" %}


## L'idée
J'ai repris cette idée d'une conf présentée au DevoxxFR 2016.
La vidéo en question : [La  vidéo](https://youtu.be/T_nrD3E5qD0?t=13m24s).

Cette vidéo était également intéressante pour les différents outils qu'elle présentait. Chaque outil permettant une découverte de la programmation selon l'âge.

Voici donc un mini-tuto pour réaliser cette construction :
![Les feux, installés sur le tapis](/assets/posts/redlights/car_with_lights.jpg)

## Conception
Pour simplifier le montage, et l'explication à fournir aux enfants, les 4 feux marchent par paires (groupe A et groupe B).
Sur notre croisement, les feux qui se font face fonctionnent ensemble.

Ensuite, avec les enfants, nous avons préparé les séquences d'allumage :
Que j'ai converti en code, sous forme de 2 tableaux (1 pour chaque paire de feux), ainsi qu'un troisième tableau pour les temps d'allumage.
Au final, il y a 6 séquences, allumant différentes LEDs sur les paires de feux, et avec des durées différentes :

 * Le vert dure 10 secondes
 * Le jaune (ou orange) dure 2 secondes
 * Le rouge dure 1 seconde

| Durée | Groupe Feu A | Groupe Feu B |
|-------|--------------|--------------|
| 10s   | vert         | rouge        |
| 2s    | orange       | rouge        |
| 1s    | rouge        | rouge        |
| 10s   | rouge        | vert         |
| 2s    | rouge        | orange       |
| 1s    | rouge        | rouge        |
| ...   | ...          | ...          |

![Schéma de séquence des feux](/assets/posts/redlights/sequence_schema.jpg) _(Talent artistique de l'année !)_

Les LEDs sont branchées en masse commune, et chaque paire de LEDs occupe un port IO du Arduino (donc, 6 au total).

Voici le premier prototype fonctionnel, avec 2 feux complets :
{% include youtubePlayer.html id="dA3wp4o4ghQ" %}

### Matériel
Je suis parti sur ce que j'avais en réserve :

 * 1 Arduino nano (ou une copie asiatique...)
 * 4 LEDs vertes
 * 4 LEDs jaunes
 * 4 LEDs rouges
 * du fil électrique, idéalement 4 couleurs différentes (pour le vert, jaune, rouge et la masse)
 * 1 boite de dérivation (pour protéger le montage)
 * (optionnellement) de quoi souder, si vous souhaitez un montage plus solide

J'ai construit les feux avec des bouts de contre-plaqué que j'ai percé au diamètre des LEDs.
Mais si vous avez la chance d'avoir accès à une imprimante 3D, il y a moyen de faire des poteaux bien plus cools et réalistes.

![les 4 feux, prêts à êtres installés](/assets/posts/redlights/lights_cabled.jpg)

J'ai installé tout ça dans un tapis de jeu illustré de routes (venant d'un célèbre designer suédois).
Le tapis a pris 5 bons coups de cutter (1 pour chaque feu, et un dernier sous la boite de dérivation), pour pouvoir glisser les fils.
Les feux ont été fixés avec de l'adhésif double-face, mais au final, ce n'est peut être pas la meilleure option (niveau solidité).

## Code et schéma
Le code tient dans un simple fichier ino (le format de l'éditeur Arduino).
Il est partagé sur Github : [ici](https://gist.github.com/chibani/ecc079ce30894ff5434bbb0690af7b68)
Ainsi, vous pourrez le copier, modifier, améliorer, etc...

Concernant le schéma, je n'ai pas trouvé de solution simple pour le faire (sans me prendre trop la tête...), d'ailleurs si vous avez, je suis preneur (mon mail et mon masto sont dans le footer).

 * D7 : feu vert du groupe A
 * D8 : feu jaune (orange) du groupe A
 * D9 : feu rouge du groupe A
 * D10 : feu vert du groupe B
 * D11 : feu jaune (orange) du groupe B
 * D12 : feu rouge du groupe B
 * les 2 masses communes sont branchés sur 2 broches GND différentes (mais j'aurai pu les brancher ensemble...).

dans le code source, les pins sont configurés dans les premières lignes.

Et une petite photo et du branchement :
![Le branchement](/assets/posts/redlights/pins_with_numbers.jpg)

Pour le chargement du code dans le Arduino, j'ai utilisé [l'IDE officielle](https://www.arduino.cc/en/Main/Software) (dispo sur Windows, Linux et OSX).
