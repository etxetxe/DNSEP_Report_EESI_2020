## Fiche synthétique de l'analyse de Getty Publications

### Auteurs
L'équipe du département numérique des éditions Getty : Ruth Evans Lane, Eric Gardner et Greg Albers.

### Esthétique
Point non pertinent pour cet objet, si ce n'est l'esthétique interne : cohérence globale de la chaîne, *beauté* des briques (Git, générateur de site statique, HTML, CSS, etc.).

### Fabrication
Il s'agit ici de tout l'enjeu : la chaîne de publication numérique est un processus de fabrication de *livres numériques* – dans l'acceptation large de "livres numériques", puisqu'il s'agit autant d'un site web, d'un fichier EPUB ou d'un fichier PDF.
Le coût de la mise en place de cette chaîne est principalement un coût humain, en temps : conception, mise en place, formation de l'équipe et des intervenants extérieurs, développement de briques (codes, logiciels intermédiaires).

### Fonctionnel
La chaîne de publication vise à répondre à plusieurs *défis* :

- fluidifier les processus de conception et de production ;
- faciliter l'intervention des différents acteurs de la maison d'édition durant les différentes phases ;
- rendre la chaîne maintenable dans le temps ;
- ne pas dépendre de logiciels dont l'évolution est incertaine ;
- permettre une longévité en terme d'accès aux fichiers, avec des formats *résilients*.

Cette chaîne de publication vise à remplacer l'assemblage de logiciels tels qu'un traitement de texte et un logiciel de PAO (publication assistée par ordinateur).

### Usage
Cette chaîne de publication s'adresse avant tout à l'équipe du département numérique de Getty Publications, cela pourrait s'élargir aux autres équipes de Getty Publications, mais aussi à d'autres maisons d'édition du milieu des musées. Le principal défi réside dans l'accessibilité des outils utilisés : Git n'est pas simple à prendre en main, des interfaces peuvent faciliter son utilisation ; les logiciels gérant les langages comme Markdown existent mais ils sont plus ou moins faciles à utiliser ; des notions en HTML sont-elles indispensables pour bien comprendre comment fonctionne la chaîne ? etc.

### Communication
Plusieurs ressources présentent cette chaîne de publication :

- [An Editor’s View of Digital Publishing](http://blogs.getty.edu/iris/an-editors-view-of-digital-publishing/), par Ruth Evan Lane, sur le blog de Getty ;
- [Building Books with Middleman Extensions](http://egardner.github.io/posts/2015/building-books-with-middleman/), par Eric Gardner, sur son blog personnel ;
- [Publier des livres avec un générateur de site statique](https://jamstatic.fr/2017/01/23/produire-des-livres-avec-le-statique/), un entretien de moi-même avec Eric Gardner, sur le site jamstatic.fr ;
- plusieurs informations sont rassemblées sur une page du site de Getty Publications : [http://www.getty.edu/publications/digital/platforms-tools.html](http://www.getty.edu/publications/digital/platforms-tools.html) ;
- [une vidéo](https://www.youtube.com/watch?v=VVYe0qR5DnM) présente le fonctionnement de cette chaîne de publication.

Il y a également eu quelques présentations publiques.

### Commercialisation
Les sources du projet sont publiées sur GitHub : [https://github.com/gettypubs](https://github.com/gettypubs). Pour le moment il n'y a pas de commercialisation de ce *workflow*.

### Ouvertures critiques
Cette chaîne de publication est originale pour plusieurs raisons :

- elle remplace totalement le couple traitement de texte et logiciel de PAO ;
- elle détourne l'utilisation d'un générateur de site statique, à l'origine conçu pour produire des sites web ;
- elle permet de générer un site web, un fichier EPUB et un fichier PDF – le PDF est utilisé pour de la consultation et pour de l'impression à la demande ;
- elle est utilisée en production, ce n'est pas un prototype.

En théorie c'est une solution très intéressante, mais elle pose deux questions principales :

- comment faciliter la prise en main et l'utilisation, notamment lorsqu'on est peu familié de Git, de Markdown, et que l'on ne sait utiliser que Word ?
- comment l'adapter pour fabriquer des livres imprimés, *papier*, en dehors de l'impression à la demande.
