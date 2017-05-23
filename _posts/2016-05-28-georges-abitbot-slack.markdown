---
layout: post
title:  "George AbitboT, le bot le plus classe du monde"
date:   2016-05-28 15:42:00 +0200
categories: fun
intro: >#
  Présentation du bot slack le plus classe du monde : George Abitbot ! Classe, ouiches et surpuissance, tout y est ...

---

## George qui ?
George AbitboT est le pendant slack de George Abitbol, l'homme le plus classe du monde.
Il est possible que vous n'ayez pas l'immense chance de connaître cet homme.  
Si tel est le cas, voici de quoi vous rattraper, avec [le flim original](https://www.youtube.com/watch?v=l44WKAtZLjI).  

George est donc l'homme le plus classe du monde.  
Ses répliques, ainsi que celles des autres personnages du flim sont cultes (pour certains, dont moi).

Ainsi, je trouvais dommage que George n'ait pas son propre bot sur Slack, histoire d'apporter de la classe à nos conversations (parce qu'il faut avouer, qu'à côté de lui, on est tous un peu just).


## Un bot pour slack

![Vous aussi, profiter pleinement de la classe](/assets/posts/georges-abitbot/conversation.png)  

Ainsi dont, je suis parti sur le développement (rapide, très rapide) d'un bot pour slack qui balancerait des citations tirées du flim aléatoirement.  
Pour communiquer avec Slack, j'ai utilisé une lib js (pour node) assez simple d'utilisation (même si je trouve le code peu pratique) : [slackbots](https://www.npmjs.com/package/slackbots).

Ensuite, j'ai récupéré un fichier de sous-titre du flim, que j'ai nettoyé et retravaillé pour pouvoir l'exploiter facilement.  
J'ai conservé environ 170 citations.

Une fois correctement configuré, le bot se connecte sur le Slack de votre choix, il suffit ensuite de l'inviter dans les channels souhaités.

Il réagit, de base, à :  
 * "george" ou "classe" : il va répondre par une citation aléatoire
 * "yep" (en début de phrase) : il va répondre aléatoirement de 1 à 5 "yep"

## Code
Le code est dispo sur Github, dans [un dépôt bien surpuissant](https://github.com/chibani/george_abitbot) !  
Vous l'aimez, vous l'admirez ? N'hésitez pas à l'essayer et le forker pour y ajouter votre classe !

Vous n'aimez pas, vous trouvez ça débile ?  
Et bien sachez que le train de vos injures roule sur le rail de mon indifférence. Je préfère me barrer plutôt que d'entendre ça plutôt que d'être sourd.

  **MONDE DE MERDE**  
  George Abitbol
