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

## Méthode pour OSX

---

## Liste des outils :
* [Terminal pour Mac](https://support.apple.com/fr-fr/guide/terminal/welcome/mac)
* [Homebrew](https://brew.sh/index_fr)
* [Git](https://git-scm.com)
* [Ruby-lang](https://rubyinstaller.org)
* [RubyGems](https://rubygems.org)
* [Jekyll](https://jekyllrb.com)
* [Atom](https://atom.io)

***

## Sommaire :

### [Avant toutes choses ...](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Fork-OSX#avant-toutes-choses-)
### [I. Homebrew](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Fork-OSX#i-homebrew-1)
### [II. IDE et dépendances](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Fork-OSX#ii-ide-et-d%C3%A9pendances-1)
#### [a. Environnement de travail](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Fork-OSX#a-environnement-de-travail-1)
#### [b. Dépendances JamStatic](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Fork-OSX#b-d%C3%A9pendances-jamstatic-1)
### [III. Clonage du dépôt de projet](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Fork-OSX#iii-clonage-du-d%C3%A9p%C3%B4t-de-projet-1)

***

## [Avant toutes choses](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Fork-OSX#sommaire-)

***

>Imaginez que vous soyez la proie de vils raptors et autres sauriens des Temps Perdus, enfermé dans un parc zoologique avec des failles de sécurité importante (la faute à un.e administrateur.ice négligent.e) et que, face au poste de contrôle du système de gestion du lieu, vous soyez la seule personne capable de remettre les compteurs en place afin de pouvoir sauver vos amis et votre famille d'une mort certaine, que serait votre première réaction ?

***

![image](https://19yw4b240vb03ws8qm25h366-wpengine.netdna-ssl.com/wp-content/uploads/This-is-a-Unix-system-I-know-this.png)

***

>Bref c'est important de tâter de la ligne de commande, ce truc affreux avec du texte blanc sur un fond noir ... C'est ce que nous allons utiliser pour cloner ce projet, vous allez voir que ça va nous faciliter la vie par la suite.

***

> Avant toute chose, il semble nécessaire de rappeler que OSX est un système UNIX de base, avec un ensemble d'outil déjà présent tel que le _**Terminal pou Mac**_ et ses commandes usuelles, le système de version _**Git**_ ainsi qu'une version de _**Ruby**_ spécifique aux Mac. Néanmoins, va être nécessaire d'installer des modules manquants pour être réellement efficace.

***

Ouvrez le _**Terminal pour Mac**_ en utilisant la barre de recherche _**Spotligth**_ (raccourcis `cmd + espace`) et tapez le nom du programme correspondant, un invité de commande devrait s'ouvrir ...

Toute les commandes UNIX sont disponibles dès le départ, pour plus d'information concernant les [commandes de base](http://devernay.free.fr/cours/unix/unixref.pdf)

***

![image](https://www.techjunkie.com/wp-content/uploads/2017/10/Search.jpg)

![image](https://eshop.macsales.com/blog/wp-content/uploads/2016/12/DefaultTerminal1280.jpg)

![image](https://store.storeimages.cdn-apple.com/4668/as-images.apple.com/is/MLA22F?wid=4000&hei=1800&fmt=jpeg&qlt=95&op_usm=0.5,0.5&.v=1496943596366)

***

Il est maintenant temps de se familiariser avec l'interface en ligne de commande :

```sh
# 'NOM_DE_SESSION'@'NOM_ORDI' désigne ici votre session suivi du nom de votre ordinateur.
# '~' désigne le niveau de profondeur de la racine du système ici au niveau session d'utilisateur avec 'NOM_DE_SESSION' comme nom de session
# '%' indique qu'une commande est prête à être tapée.

Last login: 'Day' 'Month' 'Y34r' 'H0urs':'M1nutes':'S3conds' on ttys'00*'
'NOM_DE_SESSION'@'NOM_ORDI' ~ %

# Pour commencer, la commande 'pwd' vous indiquera le chemin de votre niveau de racine actuel

'NOM_DE_SESSION'@'NOM_ORDI' ~ % pwd
/Users/'NOM_DE_SESSION'

# Entrer 'ls' vous indiquera l'ensemble des fichiers et dossiers de votre racine système

'NOM_DE_SESSION'@'NOM_ORDI' ~ % ls
Desktops

# 'cd' permet de se déplacer à travers les dossiers de la racine

'NOM_DE_SESSION'@'NOM_ORDI' ~ % cd Desktops
'NOM_DE_SESSION'@'NOM_ORDI' Desktop %
'NOM_DE_SESSION'@'NOM_ORDI' Desktop % cd ..
'NOM_DE_SESSION'@'NOM_ORDI' ~ %
```

***

## [I. Homebrew](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Fork-OSX#sommaire-)

[Homebrew](https://en.wikipedia.org/wiki/NuGet#Chocolatey) est un [gestionnaire de packages](https://fr.wikipedia.org/wiki/Gestionnaire_de_paquets) et un installateur de niveau machine en ligne de commande pour Mac OSX et les systèmes UNIX en général. Il est construit en _Ruby_ et permet d'installer les dépendances manquantes telle que la _[**GNU Compiler Collection**](https://fr.wikipedia.org/wiki/GNU_Compiler_Collection)_ pour travailler avec différents langages de programmation.

Un paquet est une archive - _fichier compressé_ - comprenant les fichiers informatiques, les informations et procédures nécessaires à l'installation d'un logiciel sur un système d'exploitation au sein d'un _agrégat logiciel_, en s'assurant de la cohérence fonctionnelle du système ainsi modifié.

***

> C'est en effet au niveau de la racine `/usr/bin` où vont se placer les fichiers d'exécution des programmes qui seront référencés dans la base de données, il est donc important que leurs chemins d'accès soient correctement établis dès l'installation, d'où le choix d'un gestionnaire de paquet à la place d'un [assistant d'installation](https://fr.wikipedia.org/wiki/Assistant_(logiciel)).

***

![image](https://brew.sh/assets/img/homebrew-social-card.png)

***

Pour installer le gestionnaire de paquet _**Brew**_ :

Ouvrez le _**Terminal pour Mac**_ en utilisant la barre de recherche _**Spotligth**_ (raccourcis `cmd + espace`) et tapez le nom du programme.

```sh
# Exécutez la commande puis entrez le mot de passe d'administrateur de votre système (en général votre mot de passe de session) pour installer les paquets.

Last login: 'Day' 'Month' 'Y34r' 'H0urs':'M1nutes':'S3conds' on ttys'00*'
'NOM_DE_SESSION'@'NOM_ORDI' ~ % /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```

***

> Comme tout système UNIX, un mot de passe de super-administrateur ou _**sudo**_ vous sera systématiquement demandé dans les cas ou le système est amené à écrire dans les fichiers de configuration, notamment lors d'une installation, afin de valider chaque action. Vous pouvez cependant passer en mode _**root**_ avec le commande `sudo su` puis votre mot de passe _**sudo**_

***

3. Attendez quelques secondes que la commande se termine.

4. Si vous ne voyez aucune erreur, vous êtes prêt à utiliser _**Homebrew**_! Tapez `brew -v` maintenant , ou consultez [Homebrew Documentation](https://docs.brew.sh) pour les instructions d'utilisation.

***

### [II. IDE et dépendances](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Fork-OSX#sommaire-)

***

#### [a. Environnement de travail](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Fork-OSX#sommaire-)

Passons à l'installation des éléments qui constitueront l'environnement de développement du futur projet.

[Atom](https://fr.wikipedia.org/wiki/Atom_(%C3%A9diteur_de_texte)) est un éditeur de texte mais surtout un _**environnement de développement intégré**_ - ou **IDE** - c'est à dire que le logiciel contient des modules qui lui permettent de gérer un grand nombre d'option dans le traitement de texte, tel que l'indexation des commandes de langage ou l'interprétation des _brackets_ - c'est à dire qu'il repère au sein d'un fichier texte les éléments qui permettent l'exécution du code.

Doté de nombreuses aides à la lecture et à l'écriture, le logiciel est également extensible via de nombreuses extensions rassemblées dans un gestionnaire de paquet intégré.

![image](https://i.ytimg.com/vi/ErpALj-8l5M/maxresdefault.jpg)

![image](https://atom-ide-community.github.io/assets/images/screenshot-linter.png)

Pour installer Atom, exécutez la commande suivante à partir du _**Terminal pour Mac**_ :

```sh

'NOM_DE_SESSION'@'NOM_ORDI' ~ % brew cask install atom
```

Si vous ne voyez aucune erreur, vous êtes prêt à utiliser Atom! Tapez atom ou `atom -v` avec le _**Terminal pour Mac**_, ou consultez Flight-Manual pour les instructions d'utilisation.

***

> Le projet à forker est composé de nombreux fichiers reliés par un ensemble de dépendances qui en assurent la structure, la description des différents modules et leurs interactions sont décrits [ici](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Cha%C3%AEne-d'%C3%A9dition).

***

#### [b. Dépendances JamStatic](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Fork-OSX#sommaire-)

***

Avant toute chose, il convient de décrire brièvement le [flux de travail](https://fr.wikipedia.org/wiki/Workflow) sur le projet de notre site :

* l'objectif est de pouvoir mettre à jour régulièrement le site par l'ajout de nouveaux articles, leurs rédactions doivent se faire de manière claire et simple avec des redirections de liens pour le vocabulaire et les chapitre pour pouvoir les modifier à la volé.

* Le mémoire fait appel à des fonctionnalités dynamique en JavaScript pour rechercher un mot dans un moteur de recherche ou convertir du HTML en PDF.

La solution a été d'utiliser un [générateur de site statique](https://fr.wikipedia.org/wiki/Jekyll_(logiciel)) qui convertis des fichiers [Markdown](https://fr.wikipedia.org/wiki/Markdown) en [HTML](https://fr.wikipedia.org/wiki/Hypertext_Markup_Language) tout en intégrant des appels de fonctions dynamique en [front-end](https://fr.wikipedia.org/wiki/Frontal_(serveur)) sans avoir besoin d'utiliser une base de donnée en [back-end](https://fr.wikipedia.org/wiki/Backend).

Écrit en [Ruby](https://fr.wikipedia.org/wiki/Ruby), [Jekyll](https://fr.wikipedia.org/wiki/Jekyll_(logiciel)) est un logiciel qui permet de générer les fichiers de conversions, d'appel et de dépendance nécessaire pour modifier le site à la volée une fois uploadé. Ce type de [pipeline](https://fr.wikipedia.org/wiki/Tube_(informatique)) porte le nom de [Jamstack](https://jamstatic.fr/2019/02/07/c-est-quoi-la-jamstack/).

***

![image](https://jekyllrb.com/img/jekyll-og.png)

***

Par défaut, le langage Ruby est installé sur les systèmes OSX, cependant il est nécessaire de faire une mise à jour afin de pouvoir installer les modules (appelés _**Gems**_) les plus récents via le gestionnaire de _**Ruby**_.

L'outil RVM est un outil entièrement dédié à la gestion des versions du langage Ruby sur votre ordinateur. Il s'agit en effet de l'acronyme de Ruby Version Manager.

```sh
# Pour installer RVM, ouvrez votre terminal et exécutez la commande suivante :

'NOM_DE_SESSION'@'NOM_ORDI' ~ % curl -sSL https://get.rvm.io | bash -s stable

# Vous devrez ensuite redémarrer le terminal. La commande 'rvm' sera alors disponible
# a commande 'rvm list known' va lister les différentes versions de Ruby. Lisez le résultat pour déterminer la version la plus récente et utilisez la commande 'rvm install' suivi du numéro de version pour lancer l'installation.

'NOM_DE_SESSION'@'NOM_ORDI' ~ % rvm list know
ruby-2.6.1
'NOM_DE_SESSION'@'NOM_ORDI' ~ % rvm install ruby-2.6.1

# Vous pouvez vérifier que la dernière version de Ruby est bien prise en compte par votre système avec la commande 'ruby -v'. Si jamais le numéro de version n'a pas changé, c'est que la plateforme Ruby n'a pas modifié le réglage qui indique la version à utiliser. Utilisez la commande suivante pour signaler à Ruby la nouvelle version :

'NOM_DE_SESSION'@'NOM_ORDI' ~ % rvm use ruby-2.6.1 --default

4. Ouvrez une nouvelle fenêtre d'invite de commande à partir du menu Démarrer, afin que les modifications apportées à la variable d'environnement PATH deviennent effectives puis Installez Jekyll et Bundler.

'NOM_DE_SESSION'@'NOM_ORDI' ~ % gem install jekyll bundler

# Vérifiez si Jekyll a été correctement installé

'NOM_DE_SESSION'@'NOM_ORDI' ~ % jekyll -v
```

Voilà, vous êtes prêt à utiliser Jekyll!

***

### [III. Clonage du dépôt de projet](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Fork-OSX#sommaire-)

![image](https://miro.medium.com/max/882/1*n5MnDrinAXeY2NpCX9H8cw.jpeg)

Avant toute chose, il convient de rappeler que, malgré leurs affinités et la manière dont ils sont amenés à être utilisé, ces deux logiciels restent utilisable de manière indépendante :

* [_**Git**_](https://fr.wikipedia.org/wiki/Git) est un logiciel libre, open-source, en local et décentralisé de _versioning_ c'est à dire que tout le monde héberge sa propre instance de fichiers ou de programme source, qui signifie en informatique une réplique d'un ensemble d'éléments de base, il est ainsi possible de travailler sur une version propre d'une instance et d'en partager les sources sans impacter les versions des autres développeurs et développeuses.
* [_**GitHub**_](https://github.com/) est un ensemble de services comprenant un système de dépôt au sein d'une base de donnée référencé, un gestionnaire et éditeur de fichier sous forme d'application web et bien d'autres, basé sur Git mais sous forme d'un système centralisé ou les développeurs travaillent et uploadent leurs instances modifiées sur le même dépôt.

Ouvrez le _**Terminal pour Mac**_ en utilisant la barre de recherche _**Spotligth**_ (raccourcis `cmd + espace`) et tapez le nom du programme correspondant, un invité de commande devrait s'ouvrir ...

Toute les commandes UNIX sont disponibles dès le départ, pour plus d'information concernant les [commandes de base](http://devernay.free.fr/cours/unix/unixref.pdf)

```sh
# Vérifiez si Git a été correctement installé.

'NOM_DE_SESSION'@'NOM_ORDI' ~ % git -v

# On va supposer que l'on souhaite travailler à la racine du disque système au sein du répertoire 'Documents' dans l'arborescence de fichiers
# Cette commande permet de se déplacer sur le répertoire 'Documents' puis d'utiliser la fonction 'clone' de git pour récupérer une copie du dépôt de fichiers à l'adresse indiqué pour l'installer au niveau du répertoire actuel 'Documents' puis de créer une nouvelle instance appelé 'Start' avant d'avant d'afficher un 'status' ou un rapport du dépôt enregistré en local.

'NOM_DE_SESSION'@'NOM_ORDI' ~ % cd Documents && git clone https://github.com/etxetxe/DNSEP_Report_EESI_2020.git && cd DNSEP_Report_EESI_2020 && git commit -m "Start" && git status

# La commande suivante permet d'exécuter sur un port réseau local à l'adresse 'localhost:4000' un déploiement du site généré.

'NOM_DE_SESSION'@'NOM_ORDI' ~ % bundle exec jekyll serve

# Ouvrez votre navigateur favoris et entrez l'url : `localhost:4000`. Si votre navigateur affiche fièrement le site, vous avez passé avec succès la phase de fork !
```

Vous êtes maintenant prêt à développer sur votre nouveau projet ! Exécutez `atom .` pour débuter sur l'éditeur de code _**Atom**_.
