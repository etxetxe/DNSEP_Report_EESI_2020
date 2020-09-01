## Fiche synthétique de la chaîne de publication d'O'Reilly
Depuis plusieurs années, voir dizaines d'années, O'Reilly fait évoluer une chaîne de publication originale et pionnière, qui n'est pas basée sur des outils d'édition classiques.

### Description
O'Reilly a mis en place une chaîne de publication, qui a évolué au fil des années selon les objectifs suivants :

1. intégrer des formats classiques, faciliter la circulation de l'information : utilisation du schéma XML DocBook permettant de travailler dans InDesign et de produire des EPUBs et des livres web facilement ;
2. automatiser la production : utilisation de XML DocBook et d'AsciiDoc ;
3. faciliter les échanges : utilisation de Git ;
4. plateforme Atlas, intégrant tous ces composants, ainsi qu'une interface en ligne.


### Auteurs
O'Reilly Media.

### Esthétique
C'est quelque peu hors sujet pour cet objet, si ce n'est l'esthétique interne : originalité de l'utilisation de XML/HTML pour faire de l'édition, développement de langages et d'outils, plateforme Atlas qui a une UI – User Interface – travaillée.

### Fabrication
C'est justement la question : une chaîne de publication est l'ensemble des méthodes/organisations et outils en vue de produire des publications/livres.

Nous pouvons nous arrêter sur les questions de format : O'Reilly Media s'appuie principalement sur XML et HTML.

### Fonctionnel
Les raisons de la mise en place de la chaîne de publication d'O'Reilly Media sont nombreuses, et différentes selon le point de vue d'où l'on se place :

- faciliter l'écriture et le suivi de l'écriture :
  - en intégrant automatiquement un fichier Word dans le *workflow* d'O'Reilly ;
  - en utilisant un langage sémantique, un éditeur de texte et un logiciel de version (Git) ;
- automatiser la production des différents formats, sans devoir dépendre de logiciels comme InDesign ou Word. À chaque modification, les différentes versions sont générées à partir d'un même format XML : PDF, EPUB, version web ;
- rendre le suivi du projet transparent : par la mise en place d'une version web à laquelle tous les intervenants du projet éditorial ont accès ;
- rendre pérenne les sources des livres, par l'utilisation de XML et de DocBook : pas de dette technique comme avec un logiciel propriétaire ;
- inventer un schéma XML pour l'édition technique avec DocBook ;
- etc.

### Usage
Cette chaîne de publication est principalement utilisée par O'Reilly Media, en interne, en tant qu'outil d'édition, de *publishing*, de qui inclut les auteurs.

C'est aussi un moyen, pour O'Reilly, de développer Atlas, une plateforme de publication qui intègre toutes les fonctionnalités présentées.


### Communication

- Lara Hogan, [Coding a book](http://larahogan.me/blog/coding-a-book/)
- [Tools of Change for Publishing](http://toc.oreilly.com/), une série de conférences organisées par O'Reilly de 2007 à 2013 ;
- Julie Steele, [So You Want to Write for O'Reilly](https://fr.slideshare.net/jsteeleeditor/so-you-want-to-write-for-oreilly-1592736/24-So_You_Want_to_Write)
- [So You Want to Write a Book?](https://web.archive.org/web/20100323163440/http://oreilly.com/oreilly/author/index.html) (version archivée, désormais remplacée par [Work with Us](http://www.oreilly.com/work-with-us.html))
- AsciiDoctor, [What is AsciiDoc? Why do we need it?](http://asciidoctor.org/docs/what-is-asciidoc/)
- [HTMLBook](https://oreillymedia.github.io/HTMLBook/)
- Matt Neuburg, [The Toolchain for My iOS Book](https://www.apeth.net/matt/iosbooktoolchain.html)

### Commercialisation
Plus que de la commercialisation, il s'agit de trouver des moyens de rentabiliser la recherche et le développement, principalement par deux façons :

- [livres](http://tdg.docbook.org/) qui présentent DocBook, le schéma XML utilisé par O'Reilly ;
- la plateforme Atlas : [https://atlas.oreilly.com/](https://atlas.oreilly.com/), mais dont l'ouverture publique n'est pas certaine ;
- Safari : la plateforme de diffusion d'O'Reilly, probablement en lien avec la chaîne de publication et peut-être Atlas.

### Ouvertures critiques
Analyse de l'évolution de la chaîne de publication : depuis un schéma XML vers une plateforme complète, logique de diffusion qui sous-tend l'ensemble des choix techniques. De quelle façon ça se passe en interne ? Quel est le choix des éditeurs (personnes) ? Recherche de l'efficacité à la base des choix techniques, même si une analyse politique des choix technologique pourrait être faite. etc.

Schématisation des priorités :

1. rentabilité, valorisation de l'image
2. pour la rentabilité : efficacité de la production et de la diffusion
3. pour l'efficacité de la diffusion : développement d'une plateforme propre
4. pour l'efficacité de la production : fluidifier les échanges, faciliter la production des formats de sortie
5. pour fluidifier les échanges : import de formats Word/etc., utilisation de Git
6. pour faciliter la production : utilisation d'un schéma XML
