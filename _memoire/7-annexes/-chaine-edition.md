# Travailler depuis les sources : guide pas-à-pas

Ce wiki constitue une manière d'illustrer ma démarche de conception, de création et d'apprentissage au sein des pratiques numériques, à travers des processus d'auto-apprentissage, de partage et de redirections.

Ainsi, ce guide vous explique comment crée un fork de mon projet de mémoire afin de pouvoir étudier son fonctionnement, soumettre des modifications et proposer une version alternative de ce dernier.

Emprunté au monde de la piraterie, un [fork](https://fr.wikipedia.org/wiki/Fork_(d%C3%A9veloppement_logiciel)) désigne une bifurcation au sein d'un projet afin de lui donner une nouvelle direction, de nouvelles entités indépendantes et autonomes sont créées mais conservent des similitudes avec le projet-mère.

***

> AVERTISSEMENT : Le tutoriel qui suit est amené à utiliser un jargon informatique qui n'est pas directement référencé dans le lexique de mon [mémoire](https://www.bifurcation.etxetxe.fr/7-annexes/lexique/).

***

La raison est que je souhaite m'adresser ici aux néophytes, dans le vocabulaire le plus accessible possible, en explicitant chaque étape nécessaire à l'exécution des opérations décrites plus bas, soit par une mise au point soit par une redirection vers une ressource annexe.

Je ne prétends pas réaliser un tutoriel de vulgarisation informatique, je n'aurais ni le recul ni le niveau de compétence nécessaire pour parvenir à une parfaite synthèse.

Je cherche avant tout à poser des briques à peu près correcte pour pouvoir faire en sorte que des points spécifiques puissent être discutés, reformulés et corrigés.

***

> Les images présentées dans cette page de tutoriel sont uniquement à but illustratif et, pour des raisons de multiplicités de versions et type de système, ne sont pas représentatifs de l'aspect visuel final de votre projet et dépendances.

***

## Sommaire :
### [Avant toutes choses ...](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Cha%C3%AEne-d%27%C3%A9dition#avant-toutes-choses--1)

***

### [I. Anatomie du dépôt](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Cha%C3%AEne-d%27%C3%A9dition#i-anatomie-du-d%C3%A9p%C3%B4t-1)
#### [_bibliographie](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Cha%C3%AEne-d%27%C3%A9dition#_bibliographie-1)
* [bibliographie.bib](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Cha%C3%AEne-d%27%C3%A9dition#bibliographie.bib-1)
#### [_includes](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Cha%C3%AEne-d%27%C3%A9dition#_includes-1)
* [footer.html](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/_includes/footer.html)
* [head.html](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/_includes/head.html)
* [header.html](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/_includes/header.html)
#### [_layouts](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Cha%C3%AEne-d%27%C3%A9dition#_layouts-1)
* [cover.html](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/_layouts/cover.html)
* [default.html](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/_layouts/default.html)
* [defaultn.html](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/_layouts/defaultn.html)
* [microtypo.html](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/_layouts/microtypo.html)
* [print.html](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/_layouts/print.html)
#### [_memoire](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Cha%C3%AEne-d%27%C3%A9dition#_memoire-1)
* ['Numéro-Chapitre'](https://github.com/etxetxe/DNSEP_Report_EESI_2020/tree/master/_memoire)

  * [-'paragraphe'.md](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/_memoire/0-remerciements/-merci.md)

  * ['paragraphe'.md](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/_memoire/0-remerciements/merci.md)
#### [_plugins](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Cha%C3%AEne-d%27%C3%A9dition#_plugins-1)
* [replace-regex.rb](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/_plugins/replace-regex.rb)
#### [_sass](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Cha%C3%AEne-d%27%C3%A9dition#_sass-1)
* [_code.scss](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/_sass/_code.scss)
* [_layout.scss](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/_sass/_layout.scss)
* [_mixins.scss](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/_sass/_mixins.scss)
* [_normalize.scss](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/_sass/_normalize.scss)
* [_pygments.scss](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/_sass/_pygments.scss)
* [_tables.scss](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/_sass/_tables.scss)
* [_typography.scss](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/_sass/_typography.scss)
#### [_wiki](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Cha%C3%AEne-d%27%C3%A9dition#_wiki-1)
* [screenshots](https://github.com/etxetxe/DNSEP_Report_EESI_2020/tree/master/_wiki)
#### [css](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Cha%C3%AEne-d%27%C3%A9dition#css-1)
* [main.scss](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/css/main.scss)
* [print.scss](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/css/print.scss)
#### [fonts](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Cha%C3%AEne-d%27%C3%A9dition#fonts-1)
* [font](https://github.com/etxetxe/DNSEP_Report_EESI_2020/tree/master/fonts)
#### [images](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Cha%C3%AEne-d%27%C3%A9dition#images-1)
* [image](https://github.com/etxetxe/DNSEP_Report_EESI_2020/tree/master/images)
#### [scripts](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Cha%C3%AEne-d%27%C3%A9dition#scripts-1)
* [lunr.min.js](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/scripts/lunr.min.js)
* [orderedList.js](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/scripts/orderedList.)
* [search.js](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/scripts/search.js)
#### [telechargements](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Cha%C3%AEne-d%27%C3%A9dition#telechargements-1)
* [telechargement](https://github.com/etxetxe/DNSEP_Report_EESI_2020/tree/master/telechargement)
#### [Autres](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Cha%C3%AEne-d%27%C3%A9dition#autres-1)
* [_config.yml](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/_config.yml)
* [.gitignore](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/.gitignore)
* [404.md](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/404.md)
* [Gemfile](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/Gemfile)
* [Gemfile.lock](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/Gemfile.lock)
* [impression.md](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/impression.md)
* [index.md](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/index.md)
* [LICENSE](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/LICENSE)
* [README.md](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/README.md)
* [recherche.html](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/recherche.html)
* [robot.txt](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/robots.txt)
* [search.html](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/search.html)
### [II. Chaîne d'édition Web](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Cha%C3%AEne-d%27%C3%A9dition#ii-cha%C3%AEne-d%C3%A9dition-web-1)
### [III. Chaîne d'édition Papier](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Cha%C3%AEne-d%27%C3%A9dition#iii-cha%C3%AEne-d%C3%A9dition-papier-1)

***

### [Avant toutes choses ...](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Cha%C3%AEne-d%27%C3%A9dition#sommaire-)

***

>Bravo ! Si vous êtes sur cette page de wiki, c'est que vous avez réussi à faire une copie du dépôt en local, auquel cas je vous invite à vous diriger à la page consacrée à [Windows](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/1.-Fork-Windows), [OSX](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/2.-Fork-OSX) ou [Linux](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/3.-Fork-Linux).

***

Nous allons maintenant voir comment travailler sur le dépôt du mémoire, la première chose à savoir est qu'un programme est un ensemble d'instruction reposant sur des chaînes de commandes comprenant entre autre des fonctions et des descriptions.

Cela signifie que l'on va avant tout s'occuper d'éditer les fichiers qui vont nous permettre de rédiger le contenu de notre mémoire, les feuilles de styles qui gèrent l'aspect visuel, d'autre les dépendances, ...

Chaque module, que l'on va décrire en premier lieu, est assigné à une ou plusieurs suites de tâches, description, ... il est donc essentiel de savoir à quoi ces derniers servent ; puisqu'il participent à créer un chaîne de conception et d'édition qui feront l'objet d'une description en [deuxième](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Cha%C3%AEne-d%27%C3%A9dition#ii-cha%C3%AEne-d%C3%A9dition-web-1) et [troisième](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Cha%C3%AEne-d%27%C3%A9dition#iii-cha%C3%AEne-d%C3%A9dition-papier-1) partie.

***

### [I. Anatomie du dépôt](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Cha%C3%AEne-d%27%C3%A9dition#sommaire-)

***

#### [_bibliographie](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Cha%C3%AEne-d%27%C3%A9dition#sommaire-)
* [bibliographie.bib](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/_bibliographie/bibliographie.bib)

Ce fichier contient l'ensemble des références bibliographiques enregistrées au format [BibTex](https://fr.wikipedia.org/wiki/BibTeX) utilisées pour les citations dans les textes. Pour plus de commodités, il est possible d'utiliser un logiciel comme [Zotero](https://fr.wikipedia.org/wiki/Zotero) afin de générer votre bibliographie au fur et à mesure.

Pour émettre une citation dans le texte rédactionnel, il faut insérer la formule : `{& cite 'nom_de_votre_réference' &}` derrière votre texte. Il est possible de modifier les informations de votre référence dans le fichier `.bib` référencé.

L'affichage de la bibliographie se fait avec la formule : `{& bibliography --query @'type_article' &}` dans un fichier consacré à la rédaction des pages d'articles.


***

![image](https://bifurcation.etxetxe.fr/images/bibliographie.png)

***

#### [_includes](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Cha%C3%AEne-d%27%C3%A9dition#sommaire-)

Ce dossier contient l'ossature des pages HTML générées par _**Jekyll**_ durant le processus de compilation final du site.

* [footer.html](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/_includes/footer.html)

Ce fichier HTML permet d'intégrer dans la génération de page web le code HTML correspondant aux informations que l'on trouve en bas de la page de votre site, une section correspond aux hyperliens de référence tandis l'autre est un script permettant de créer un menu vertical déroulant du site.

* [head.html](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/_includes/head.html)

Ce fichier HTML correspond aux information qui seront lues en premier par votre navigateur, il correspond à la carte d'identité de votre site web et ce qui lui permet de pouvoir être référencé par les moteurs de recherche, dans le cas où le [SEO](https://fr.wikipedia.org/wiki/Optimisation_pour_les_moteurs_de_recherche) serait important dans la diffusion de votre projet.

* [header.html](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/_includes/header.html)

Ce fichier HTML correspond à l'organisation du menu vertical déroulant constituant l'en-tête du site web car c'est à partir de ce dernier auquel on accède à l'ensemble des parties du site.

***

![image](https://bifurcation.etxetxe.fr/images/includes.png)

***

#### [_layouts](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Cha%C3%AEne-d%27%C3%A9dition#sommaire-)

Ce dossier contient les feuilles sémantiques contenant les fichiers **_includes** précédents et organisant un ensemble de patrons destinées à être utilisés spécifiquement selon le type de page web que l'on veut faire.

* [cover.html](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/_layouts/cover.html)

Ce fichier HTML correspond à une feuille de style attribuant la structure sémantique de la page de couverture du site web.

* [default.html](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/_layouts/default.html)

Ce fichier HTML correspond à une feuille de style attribuant la structure sémantique des pages rédactionnelles du site web.

* [defaultn.html](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/_layouts/defaultn.html)

Ce fichier HTML correspond à une feuille de style attribuant la structure sémantique des pages rédactionnelles du site web. A noter que cette variation supprime la numérotation des paragraphes.

* [microtypo.html](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/_layouts/microtypo.html)

Une redirection d'appel de fonction d'un composant de fichier [Gemfile](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/Gemfile) permettant d'intégrer les ponctuations française.

* [print.html](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/_layouts/print.html)

Ce fichier HTML correspond à une feuille de style attribuant la structure sémantique de la page [_print-to-html_](http://strabic.fr/Workshop-PrePostPrint) dont le processus sera décrit en détail dans la [partie 3](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Cha%C3%AEne-d%27%C3%A9dition#iii-cha%C3%AEne-d%C3%A9dition-papier-1)

***

![image](https://bifurcation.etxetxe.fr/images/default.png)

***

#### [_memoire](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Cha%C3%AEne-d%27%C3%A9dition#sommaire-)

Ce dossier, qui est parmi les plus important de se dépôt, est dédié à la rédaction en lui-même du contenu de ce mémoire. Le langage [Markdown](https://fr.wikipedia.org/wiki/Markdown) est utilisé car il permet de rédiger en HTML de manière simplifiée sans avoir à connaître l'ensemble des balises.

* ['Numéro-Chapitre'](https://github.com/etxetxe/DNSEP_Report_EESI_2020/tree/master/_memoire)

  * [-'paragraphe'.md](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/_memoire/0-remerciements/-merci.md)

Ce fichier MarkDown contient la partie rédactionnelle des pages du site web.

  * ['paragraphe'.md](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/_memoire/0-remerciements/merci.md)

Ce fichier Markdown contient un appel de fonction en [YAML](https://fr.wikipedia.org/wiki/YAML) permettant d'organiser les liaisons entre les différentes pages du site web.

***

![image](https://bifurcation.etxetxe.fr/images/memoire.png)

***

#### [_plugins](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Cha%C3%AEne-d%27%C3%A9dition#sommaire-)

Ce greffon permet entre autre de remplacer les chaînes de caractère entre parenthèse `{{chaîne.de.caractère}}` entre autre mais permet surtout d'intégrer les fonctions [Liquid](https://shopify.github.io/liquid/) au sein d'un générateur _**Jekyll**_.

* [replace-regex.rb](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/_plugins/replace-regex.rb)

***

![image](https://bifurcation.etxetxe.fr/images/replace_regex.png)

***

#### [_sass](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Cha%C3%AEne-d%27%C3%A9dition#sommaire-)

Ce dossier contient  les fichier de composition de feuille de style écrits en [SASS](https://fr.wikipedia.org/wiki/Sass_(langage))

* [_code.scss](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/_sass/_code.scss)

Ce fichier SCSS permet de modifier le style visuel des inserts de code `exemple_de_code` sur les pages du site web.

* [_layout.scss](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/_sass/_layout.scss)

Ce fichier SCSS permet de modifier le style visuel des feuilles de [style sémantique](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Cha%C3%AEne-d%27%C3%A9dition#_includes-1) sur les pages du site web.

* [_mixins.scss](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/_sass/_mixins.scss)

Ce fichier SCSS permet de modifier le style visuel des appels de fonction [WebKit](https://fr.wikipedia.org/wiki/WebKit) présentes sur certains navigateurs.

* [_normalize.scss](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/_sass/_normalize.scss)

Ce fichier SCSS permet d'ajuster les appels de fonction [WebKit](https://fr.wikipedia.org/wiki/WebKit) sur les navigateurs et systèmes embarqués susnommés.

* [_pygments.scss](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/_sass/_pygments.scss)

Ce fichier SCSS permet de référencer l'ensemble des paramètres liés à la mise en couleur du texte.

* [_tables.scss](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/_sass/_tables.scss)

Ce fichier SCSS permet d'ajuster le style visuel de l'arrière plan de la page web.

* [_typography.scss](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/_sass/_typography.scss)

Ce fichier SCSS permet de référencer l'ensemble des paramètres liés à la typographie

***

![image](https://bifurcation.etxetxe.fr/images/scss.png)

***

#### [_wiki](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Cha%C3%AEne-d%27%C3%A9dition#sommaire-)
* [screenshots](https://github.com/etxetxe/DNSEP_Report_EESI_2020/tree/master/_wiki)

Ce dossier contient l'ensemble des images utilisées dans les wikis du projet et qui ne sont pas référencées sur le web.

***

#### [css](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Cha%C3%AEne-d%27%C3%A9dition#sommaire-)
* [main.scss](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/css/main.scss)

Ce fichier SCSS constitue la feuille de style utilisée sur la version web du mémoire et qui inclus l'ensemble des fichiers du dossier [**_sass**](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Cha%C3%AEne-d%27%C3%A9dition#_sass-1)

* [print.scss](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/css/print.scss)

Ce fichier SCSS constitue la feuille de style utilisée sur la version PDF du mémoire, généré avec l'outil [PagedJS](https://www.pagedjs.org/) dont l'usage sera expliqué dans la [partie 3](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Cha%C3%AEne-d%27%C3%A9dition#iii-cha%C3%AEne-d%C3%A9dition-papier-1) du wiki.

***

![image](https://bifurcation.etxetxe.fr/images/css_js.png)

***

#### [fonts](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Cha%C3%AEne-d%27%C3%A9dition#sommaire-)
* [font](https://github.com/etxetxe/DNSEP_Report_EESI_2020/tree/master/fonts)

Ce dossier contient l'ensemble des fontes et de leurs variations utilisées pour le mémoire au format [.woff](https://fr.wikipedia.org/wiki/Web_Open_Font_Format).

***

#### [images](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Cha%C3%AEne-d%27%C3%A9dition#sommaire-)
* [image](https://github.com/etxetxe/DNSEP_Report_EESI_2020/tree/master/images)

Ce dossier contient l'ensemble des images utilisées dans le mémoire et qui ne sont pas référencées sur le web.

***

#### [scripts](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Cha%C3%AEne-d%27%C3%A9dition#sommaire-)
* [lunr.min.js](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/scripts/lunr.min.js)

Ce script Javascript permet d'extraire une chaîne de caractère au sein des paragraphes et des en-têtes des fichiers HTML. Il s'agit d'un élément du greffon [jekyll-lunr-js-search](https://github.com/slashdotdash/jekyll-lunr-js-search)

* [orderedList.js](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/scripts/orderedList.)

Ce script Javascript permet d'utiliser [PagedJS](https://www.pagedjs.org/) et inclus également des routines de préprocesseur lors de l'affichage par le navigateur web

* [search.js](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/scripts/search.js)

Ce script Javascript permet de gérer les appels de recherches et de réponses via le navigateur. Il s'agit d'un élément du greffon [jekyll-lunr-js-search](https://github.com/slashdotdash/jekyll-lunr-js-search)

***

#### [telechargements](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Cha%C3%AEne-d%27%C3%A9dition#sommaire-)
* [telechargement](https://github.com/etxetxe/DNSEP_Report_EESI_2020/tree/master/telechargement)

Ce dossier contient le fichier PDF généré avec [PagedJS](https://www.pagedjs.org/), dont l'usage sera expliqué dans la [partie 3](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Cha%C3%AEne-d%27%C3%A9dition#iii-cha%C3%AEne-d%C3%A9dition-papier-1) du wiki.

***

#### [Autres](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Cha%C3%AEne-d%27%C3%A9dition#sommaire-)

***

* [_config.yml](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/_config.yml)

Ceci est le fichier de configuration écrit en [YAML](https://fr.wikipedia.org/wiki/YAML) qui permet de faire appel aux fonctions [Liquid](https://shopify.github.io/liquid/) afin de remplacer les `{{chaîne.de.caractère}}` par les éléments présent dans ce fichier-ci.

***

![image](https://bifurcation.etxetxe.fr/images/config_yml.png)

***

* [.gitignore](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/.gitignore)

Ce fichier permet de ne pas ajouter dans le suivi de version de -**Git**_ certains dossiers ou fichiers et également de ne pas les inclure dans la génération du site avec _**Jekyll**_.

* [404.md](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/404.md)*

Ce fichier MarkDown permet de rédiger la page d'Erreur [404](https://fr.wikipedia.org/wiki/Erreur_HTTP_404) qui sera ajoutée durant la génération du site avec _**Jekyll**_.

***

![image](https://bifurcation.etxetxe.fr/images/404_index_readme_gitignore_gemfile_license_impression_license.png)

***

* [Gemfile](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/Gemfile)

Ce fichier Ruby contient l'ensemble des sources de greffons Ruby appelé _**gem**_ qui permettent de générer notre serveur Ruby et entre autre utiliser _**Jekyll**_.

* [Gemfile.lock](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/Gemfile.lock)

Ce fichier Ruby contient l'ensemble des extensions des sources de greffons Ruby appelé _**gem**_ qui permettent de générer notre serveur Ruby et entre autre utiliser _**Jekyll**_.

* [impression.md](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/impression.md)

Ce fichier MarkDown permet de rédiger impression.html qui sera ajoutée durant la génération du site avec _**Jekyll**_ et qui utiise la feuille sémantique **print.html** dans [_includes](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Cha%C3%AEne-d%27%C3%A9dition#_includes-1)

* [index.md](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/index.md)

Ce fichier MarkDown permet de rédiger index.html qui sera ajoutée durant la génération du site avec _**Jekyll**_ et qui utiise la feuille sémantique **cover.html** dans [_includes](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Cha%C3%AEne-d%27%C3%A9dition#_includes-1)

* [LICENSE](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/LICENSE)

Ce fichier texte est une reproduction de la licence en vigueur sur le projet.

Pour les contenus du site, licence CC BY-NC-SA : [Creative Commons Attribution - Pas d’Utilisation Commerciale - Partage dans les Mêmes Conditions](https://creativecommons.org/licenses/by-nc-sa/4.0/).

* [README.md](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/README.md)

Ce fichier MarkDown contient les informations importantes concernant le dépôt en général et la démarche de conception qui y est recherchée.

* [recherche.html](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/recherche.html)

Ce fichier permet de créer une page de navigation pour entrer et exécuter une recherche.

* [robot.txt](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/robots.txt)

***

> Négligeable mais peut-être permet-il de filtrer le référencement ?

***

* [search.html](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/search.html)

Ce fichier permet de créer une page de navigation pour faire défiler des recherche.

***

![image](https://bifurcation.etxetxe.fr/images/site_touch_apple_recherche_search.png)

***

### [II. Chaîne d'édition Web](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Cha%C3%AEne-d%27%C3%A9dition#sommaire-)

***

Pour comprendre les raisons de mettre en place une chaîne d'édition pour le web, il est important de savoir que la grande difficultés de publier un carnet de recherche en ligne est lié à différents facteurs, qu'ils soient humains, technique ou lié au contenu :

* La personne derrière un travail de recherche en ligne doit s'assurer qu'elle est capable de comprendre et de se mettre à la place de l'ensemble des corps intermédiaires de l'écriture jusqu'à la publication de son travail en passant par la réception des retours de spécialistes pour appuyer ou contredire certains points nécessaires.

* La personne intéressé doit également se former aux bases du Web, que ce soient les langages de programmation comme les solutions d'hébergement entre autre, ou trouver une personne capable, moyennant rémunération, de réaliser de A à Z la création et la maintenance d'un site web. Tout dépend du degré d'investissement que le chercheur est prêt à mettre, s'il désire tout créer seul _ex nihilo_, sous-traiter à un collaborateur ou collaboratrice ou bien utiliser un [système de gestion de contenu](https://fr.wikipedia.org/wiki/Syst%C3%A8me_de_gestion_de_contenu) prêt à l'emploi.

* Enfin, et c'est le cœur-même du travail de recherche, s'assurer que ce que l'on énonce puisse être validé par des arguments, des expériences ou en tout cas des preuves vérifiables et accessibles via des sources sûres. Par conséquent, le contenu doit pouvoir être révisé par de multiples corrections au fur et à mesure.

Le cycle d'un travail de recherche s'accorde cependant moins facilement avec des manières de faire itératives ainsi que par des récits personnels, pourtant il faut noter que l'expérience subjective, bien qu'elle ne soit pas une finalité en tant que sujet dans la recherche, est aussi un élément important, qui permet entre autre de défricher les voies dans lesquelles on ne s'est pas encore égaré durant une errance.

Dans le cas de mon projet de mémoire, j'ai choisi de m'appuyer sur un environnement de travail utilisé par [quelqu'un d'autre](https://gitlab.com/antoinentl/systeme-modulaire-de-publication) à la place d'un CMS de type [Wordpress](https://wordpress.org/) car il était nécessaire pour moi d'échapper au complexe de la [boîte noire](https://fr.wikipedia.org/wiki/Boîte_noire_(système)) qui est [mentionné dans ma recherche]() et également parce que le partage et la transmission d'une expérience sont des éléments important pour le développement de toute pratique numérique.

Un [générateur de site statique](https://github.com/vpoulailleau/site_statique) va permettre de convertir un ensemble de fichier en page HTML statique que l'on va pouvoir uploader sans avoir besoin d'utiliser une base de donnée pour générer des fichiers à la volé. On peut définir différents type de fichiers de travail sur lesquelles on va pouvoir intervenir :

* Le balisage rédactionnel concerne le travail d'écriture du contenu, ce que le lecteur doit lire avant tout.
* Le balisage sémantique concerne la structuration et la relation du contenu avec les différentes typologies d'information possible
* Le balisage stylistique concerne la mise en forme du contenu afin de différencier et signifier les différentes informations.
* Le balisage applicatif concerne la couche dynamique d'exécution des scripts.

Avant de mettre en ligne votre projet web, il est important de vous poser les questions concernant vos souhaits, les moyens ou les compétences techniques que vous avez :

* Un serveur web autogéré de type [Apache](apache.org) ou [NGINX](https://www.nginx.com/) n'est pas vraiment recommandé si vous n'êtes pas rompu à la création et à la gestion de serveurs persistant mais nous n'aurez pas besoin de louer du stockage chez un hébergeur.

* Vous pouvez également réserver à l'année un nom de domaine ou [DNS](https://fr.wikipedia.org/wiki/Domain_Name_System) qui redirige l'adresse IP de votre serveur vers un domaine plus précis pour qu'il puisse être référencé par les moteurs de recherche. Vous pouvez comparer les offres présentes chez des hébergeurs comme [OVH](https://www.ovh.com/fr/domaines/) ou [Infomaniak](https://www.infomaniak.com/fr/domaines).

* Vous pouvez également utiliser un [CDN](https://fr.wikipedia.org/wiki/R%C3%A9seau_de_diffusion_de_contenu) pour afficher les pages web présentes dans vos dépôts. De base gratuite, il est également possible d'avoir des propositions forfaitaires pour un stockage illimité et un streaming de contenu vidéo par exemple. Vous pouvez comparer les offres présentes chez des hébergeurs comme [GitHub Pages](https://pages.github.com/) ou [Netlify](https://www.netlify.com/).

La dernière solution correspond à un équilibre entre le coût financier (l'hébergement est gratuit dans notre cas) et la simplicité d'utilisation, car une fois le projet en ligne, toutes modifications dans le dépôt met automatiquement le site à jour.

Mais avant d'en arriver là, il faut héberger notre projet en créant un dépôt sur des sites de forges comme [GitLab](https://gitlab.com/users/sign_in), [GitHub](https://github.com/login) ou [Bitbucket](https://bitbucket.org/). Il faudra ensuite lier le dépôt local du dossier de travail vers le dépôt distant en ajoutant un URL de connexion puis exécuter les commandes suivantes à l'aide du terminal _**Git Bash**_:

```bash
# pour initialiser le dépôt local

'SESSION'@'NOM_ORDI' MINGW64 ~/Documents/DNSEP_Report_EESI_2020 (master)
$ git init

# pour ajouter l'URL de connexion, vous serez amené à taper le mot de passe de votre identifiant de dépôt de forge pour synchroniser une fois pour toute votre dépôt local avec celui distant.

'SESSION'@'NOM_ORDI' MINGW64 ~/Documents/DNSEP_Report_EESI_2020 (master)
$ git remote add origin git@'adresse_du_dépôt':'utilisateur_du_dépôt'/'nom_du_dépôt'.git

# pour ajouter toutes les modifications locales.

'SESSION'@'NOM_ORDI' MINGW64 ~/Documents/DNSEP_Report_EESI_2020 (master)
$ git add .

# pour créer un nouveau commit du projet dans la base de donnée du répertoire HEAD du dossier .git c'est à dire une sauvegarde des modifications effectuées sur les fichiers à un instant T.

'SESSION'@'NOM_ORDI' MINGW64 ~/Documents/DNSEP_Report_EESI_2020 (master)
$ git commit -m "modification"

# pour créer une nouvelle branche et y bifurquer afin de travailler sur des voies parallèles.

'SESSION'@'NOM_ORDI' MINGW64 ~/Documents/DNSEP_Report_EESI_2020 (master)
$ git branch "'nom'" && git switch "'branch'"

# pour vérifier l'état du dépôt local.

'SESSION'@'NOM_ORDI' MINGW64 ~/Documents/DNSEP_Report_EESI_2020 ('nom')
$ git status

# pour envoyer les fichiers du dépôt local vers le dépôt distant.

'SESSION'@'NOM_ORDI' MINGW64 ~/Documents/DNSEP_Report_EESI_2020 ('nom')
$ git push origin 'nom_de_la_branche'

# pour récupérer en local les modifications effectuées sur le dépôt distant.

'SESSION'@'NOM_ORDI' MINGW64 ~/Documents/DNSEP_Report_EESI_2020 ('nom')
$ git pull origin 'nom_de_la_branche'
```

***

> Il est parfois intéressant d'utiliser des exemples visuelles pour comprendre comment marche un système, ici [_**Git**_ expliqué avec des chats](https://girliemac.com/blog/2017/12/26/git-purr/)

***

Après avoir créé un dépôt et commencé à travailler dessus, il est temps de mettre de site en ligne : la méthode va se concentrer sur le CDN [Netlify](https://app.netlify.com/), choisissez le dépôt de forge dans lequel vous travailler puis identifier vous pour le synchroniser avec le CDN.

Choisissez le dépôt ou se trouve le site à faire héberger pour ensuite accéder au menu de configuration du projet à déployer.

***

![image](https://bifurcation.etxetxe.fr/images/netlify.png)

***

> Vous pouvez également utiliser un nom de domaine personnalisé en récupérant les adresses de serveur dans les paramètres DNS de votre site hébergé et en remplaçant sur votre gestionnaire de DNS de votre hébergeur les adresses de serveur par celles personnalisées afin de faire une redirection de DNS

***

![image](https://bifurcation.etxetxe.fr/images/dns.jpg)

***

### [III. Chaîne d'édition Papier](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Cha%C3%AEne-d%27%C3%A9dition#sommaire-)

***

![image](https://bifurcation.etxetxe.fr/images/pagedjsA.png)

***

![image](https://bifurcation.etxetxe.fr/images/pagedjsB.png)
