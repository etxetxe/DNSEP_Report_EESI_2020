# Un mémoire sur les chaînes de publication
Ceci est le dépôt du mémoire sur les chaînes de publication d'[Antoine Fauchié](https://www.quaternum.net/) : *Vers un système modulaire de publication : éditer avec le numérique*.

Ce mémoire, sous la direction d'[Anthony Masure](http://www.anthonymasure.com/) et de [Marcello Vitali-Rosati](http://vitalirosati.com/), est réalisé dans le cadre d'une Validation des acquis de l'expérience (VAE) en Master 2 Publication numérique à l'[enssib](http://www.enssib.fr/).

Ce dépôt a vocation à donner à voir un travail de recherche et d'écriture en cours, plutôt qu'à rassembler des contributions – même si celles-ci sont possibles et bienvenues.
Vous pouvez suivre les évolutions ([activity](https://gitlab.com/antoinentl/systeme-modulaire-de-publication/activity)), les phases d'écriture ([commits](https://gitlab.com/antoinentl/systeme-modulaire-de-publication/commits/master) et [branches](https://gitlab.com/antoinentl/systeme-modulaire-de-publication/branches)) et les échanges ([issues](https://gitlab.com/antoinentl/systeme-modulaire-de-publication/issues)) sur ce dépôt.

Ce mémoire prend la forme d'un site web dédié, lisible plus facilement que des fichiers dans un dépôt Git :

[https://memoire.quaternum.net](https://memoire.quaternum.net)

Pour en savoir plus sur cette démarche : [Un mémoire en dépôt](https://www.quaternum.net/2018/06/04/un-memoire-en-depot/) sur quaternum.net.


## Vers un système modulaire de publication : éditer avec le numérique
Ce mémoire tente d'interroger différents modèles de chaînes de publication ou d'édition – au sens d'un ensemble de méthodes et d'outils pour concevoir, fabriquer et produire des livres.
Partant du principe que le numérique – et plus particulièrement les méthodes et les technologies issues du développement web – bouleverse grandement les chaînes d'édition, comment peut-on adapter ou modifier ces _chaînes_ et envisager un système modulaire ?
Plus globalement, si le livre numérique est une nouvelle approche de l'écrit tant dans sa diffusion que dans sa réception, n'y a-t-il pas en filigrane des changements plus profonds dans la manière de _faire_ des livres ?

Ce mémoire s'articule autour de quatre piliers :

1. des commentaires de texte, point de départ pour comprendre, analyser et peut-être critiquer notre rapport au livre numérique et plus largement à la technologie ;
2. des analyses de cas pour faire émerger des modèles alternatifs, les comprendre et les décortiquer, matière pour construire des propositions ;
3. des propositions pour entrevoir un nouveau modèle de système modulaire de publication ;
4. des entretiens pour éprouver ce système modulaire dans des situations aussi diverses que concrètes.

Ce mémoire a comme point de départ ce billet écrit en mars 2017 : [Une chaîne de publication inspirée du web](https://www.quaternum.net/2017/03/13/une-chaine-de-publication-inspiree-du-web/)

## Bibliographie
Une bibliographie, sous forme de Groupe Zotero, est disponible par ici : [https://www.zotero.org/groups/2191614/](https://www.zotero.org/groups/2191614/).


## Un dépôt ?

### Architecture du dépôt
Différents documents de travail sont placés dans `/materiaux/`, et ne sont pas publiés en dehors du dépôt.
Les fichiers qui constituent le mémoire sont placés dans `_memoire`.
Il y a donc des doublons entre des fichiers de `/materiaux/` et des pages du site – certains travaux existent d'abord dans `/materiaux/` avant d'être déplacés et remodelés dans le dossier `_memoire` nécessaire au générateur de site statique.

Les branches correspondent à différents phases de travail, la branche `master` étant la version finale et publique.
Il est possible d'intervenir dans les autres branches, qui sont donc des étapes intermédiaires de recherche et de rédaction.

### Le choix de GitLab
Pourquoi avoir choisi [GitLab](https://about.gitlab.com/) plutôt que [GitHub](https://github.com/about) ou [Framagit](https://framagit.org/) ?
Pour éviter l'_effet de silo_ de GitHub tout en facilitant l'interaction – la création d'un compte GitLab est peut-être plus commune que celle d'un compte Framagit –, et en profitant de certaines fonctionnalités de [GitLab](https://about.gitlab.com/blog/categories/releases/).


## Un générateur de site statique
Pour produire les différentes versions du mémoire, le générateur de site statique [Jekyll](https://jekyllrb.com/) est utilisé, ainsi que différentes briques, pour la branche beta le site est déployé avec GitLab CI/CD.


## Conventions

### Écriture
Pour faciliter le travail de commentaire et de validation : une phrase par ligne.
Les langages de balisage léger comme Markdown ou AsciiDoc n'interprètent pas le _saut de ligne_.

### Usages de Git
Pour rendre l'utilisation de Git plus compréhensible, voici une liste de conventions pour la rédaction des _commits_ :

- `admin` : gestion technique du dépôts ou du site
- `style` : mise en forme
- `edit` : édition de contenus
- `fix` : correction, modification suite à une remarque
- `org` : organisation des fichiers, du dépôt, du site
- `gen` : automatisation de la génération des différentes formes et formats
- `test` : essai (mais normalement cela est signalé dans une branche spécifique)

## Licence
Pour les contenus du site, licence CC BY-NC-SA : [Creative Commons Attribution - Pas d’Utilisation Commerciale - Partage dans les Mêmes Conditions](https://creativecommons.org/licenses/by-nc-sa/4.0/).

## Contact
[antoine@quaternum.net](mailto:antoine@quaternum.net) ou [@antoinentl@mamot.fr](https://mamot.fr/@antoinentl)
