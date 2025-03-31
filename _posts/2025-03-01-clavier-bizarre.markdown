---
layout: post
title: Clavier bizarre
date:   2025-03-28 08:37:00 +0200
thumbnail: /assets/posts/clavier-bizarre/ferris.jpg
categories: geekeries
intro: >#
  Les claviers, c'est comme votre pot de pâte à tartiner favorite, quand on tombe dedans, on n'est pas prêt(e)s d'en sortir...

---
![Photo clavier split type Ferris](/assets/posts/clavier-bizarre/ferris.jpg)


## Contexte
Il y a quelques années, j'ai acheté mon premier clavier mécanique, au format "standard", mais "réduit".
Un Keychron K6, un clavier qui cochait, pour moi, et à l'époque, pas mal de cases :

- Clavier mécanique
- hot-swappable (même si je n'ai jamais changé les switches d'origine...)
- sans fil, avec 3 profils d'appairage, et utilisable également en mode filaire (USB-C)
- autonomie plus que correcte (plusieurs semaines)
- relativement compacte (on parle d'un 65%, c'est à dire qu'on reste assez proche d'un clavier d'ordinateur portable)

Malheureusement :

- QWERTY, donc phase d'adaptation pour le Français que je suis, habitué à l'AZERTY et aux touches accentuées
- trop massif et lourd pour être emmené facilement partout
- assez haut, donc contrainte sur les mains/poignets
- disposition "standard" (ANSI), donc peu ergonomique

Au fil des ans, mon K6 me convenait, MAIS, je commençais à avoir des tensions dans les mains (canal carpiens, et compagnie).
Je ne pouvais pas facilement l'emmener au bureau, donc sur place je me rabattais sur le clavier AZERTY "classique" présent sur mon ordinateur de travail. Obligé de reprendre des habitudes pour quelques jours, puis retour à la maison...

Je me suis donc mis en quête d'une nouvelle monture pour :

- Avoir une meilleure ergonomie
- Pouvoir le transporter, donc ne pas avoir à changer trop souvent
- Tenter de taper avec tous mes doigts

Et après la lecture des [aventures de Clément dans le monde des claviers](https://blog.clement.delafargue.name/posts/2024-03-04-keyboardic-apocalypse.html), j'ai décidé de sauter le pas.

## "C'est un clavier ça ???"

L'image en tout début d'article présente effectivement mon clavier actuel : un [Aurora Sweep](https://splitkb.com/products/aurora-sweep), proposé (en kit) par SplitKB.
C'est un dérivé du [Ferris Sweep](https://github.com/davidphilipbarr/Sweep) (lui-même une itération du [Ferris](https://github.com/pierrechevalier83/ferris), oui c'est sans fin), avec quelques ajouts :

- Rétro-éclairé en RGB
- Possibilités de mettre 2 petits écrans OLED
- compatible avec des "tenting puck" (supports pour visser des supports...)

Alors oui, c'est particuliers, les lettres sont "nus" (blank), mais je vous assure que ça marche.

### 34-36 touches ? Est-ce suffisant ?

Le Ferris Sweep fait partie des claviers très très léger en nombre de touches. Avec seulement 34 en tout (3x5 pour les "doigts" et 2 touches par pouce), ça réduit pas mal face aux claviers standards et leur centaine de touches.
Mais du coup, "OK t'arrive à avoir l'alphabet, mais comment tu tapes les autres lettres ? Et les chiffres ??? Les accents ???".

Pour ça, j'utilise des `layers`, ou des "calques" en français.
En gros, j'ai plusieurs configurations possibles pour chaque touche, pour qu'elle devienne le caractère que je souhaite.
Pour "activer" chaque layer, je maintiens appuyée une des touches habituelles. Par exemple, une appui long sur `L` active le layer des nombres (123... et les signes associées : "+-*/=").
Dans l'idée, c'est comme quand vous appuyez sur `Alt-GR` pour écrire un `@` ou `|`, sauf que moi je fais `L+Maj+D` pour `@` et `F+I` pour `|` .

Il en va de même pour les chiffres, fonctions, accents, ...

Et ainsi, au fil des besoins, je structure/modifie mes layers, car rien n'est figé ce qui permet de paufiner sa configuration pour tirer le meilleur de son clavier.

### Et comment on crée ces layers et cette configuration ?

Il existe dans cet univers, 2 grandes familles de firmware : [QMK Firmware](https://qmk.fm/) et [ZMK](https://zmk.dev/). (je vous épargne `RMK`, et les plus éxotiques).

L'un comme l'autre permettent plus ou moins les mêmes choses (layers, macros, raccourcis, etc...), mais ZMK est plus récent et surtout il prend en charge les claviers sans-fil (via Bluetooth).

Aussi, QMK n'est pas compatible avec certaines cartes contrôleur (notamment la famille des [nrf5x](https://github.com/joric/nrfmicro/wiki/QMK), pour des problèmes de licences).

Même si je me suis fait la main sur QMK, car au départ mon clavier était équipé de [microcontrôleurs Liatris](https://splitkb.com/products/liatris), j'ai été contraint d'en changer et ait opté pour du nice-nano v2, seulement compatibles ZMK.

## Et si je veux m'y mettre ?

Déjà : essayer. Alors je sais, c'est pas tous les 4 matins qu'on croise de tels claviers, mais je peux volontiers faire une démo ou même essayer mon clavier (infos de contact dans le footer).

Pour du kit "simple", avec une doc très fournie, du matériel de qualité (testé), je recommande [SplitKB.com](https://splitkb.com/), ils proposent des évolutions des modèles "courants" (Sweep Ferris, Corne, etc...).

On trouve aussi des copies pas bien chères sur AliExpress. Quelques revues sont présentes sur [Reddit](https://www.reddit.com/r/ErgoMechKeyboards/search/?q=aliexpress), je vous incite fortement à aller voir avant de lâcher 50-100 balles car certains peuvent avoir des conceptions particulières ou des défauts de fabrication.

## Ressources pour aller plus loin

### ZMK

[Editeur de keymap en ligne](https://nickcoutsos.github.io/keymap-editor/)

Ensemble de configurations, notamment pour les combos ZMK et autres tap-mods
[Exemple de configuration avancée, pour des 34 keys](https://github.com/urob/zmk-config)

Ma config actuelle : [chibani/zmk-config](https://github.com/chibani/zmk-config) (travail en cours, tout n'est pas à jour, à commencer par le README).

### Communautés

Il existe un Discord géré par les gens de Splitkb.com . La communauté est très accueillante et vous pourrez y obtenir des coups de mains salvateurs.

Il y a un chan Reddit [ErgoMechBoards](https://www.reddit.com/r/ErgoMechKeyboards/) , avec principalement du "show and tell" (des gens se montrent leurs claviers) mais il est également possible d'y demander de l'aide.

### Se faire la main

Même si j'étais à mon aise sur mon clavier K6 (65%) et sa disposition QWERTY, passer au Ferris a demandé un certain temps d'adaptation. En somme, il faut réapprendre à ~~marcher~~ taper.
Il m'a fallut, en gros, un bon mois pour taper sans trop galérer avec les lettres et les caractères accentués.
Ensuite, pour les autres (chiffres, caractères spéciaux, fonctions...), c'est toujours en cours, mais je ne réfléchis presque plus pour trouver ces combinaisons.

S'entrainer, 15-30 minutes par jour aide énormément à s'habituer à un changement de layout.
J'utilise (presque-)régulièrement : [KeyBR.com](https://www.keybr.com/fr), un site d'entrainement à la dactylographie. C'est gratuit, bien foutu, et en créant un compte, on peut suivre sa progression.
