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

## Méthode pour Windows

***

## Liste des outils :

* [Windows Powershell](https://docs.microsoft.com/fr-fr/powershell)
* [Chocolatey](https://chocolatey.org)
* [Mingw-w64-GCC](http://mingw-w64.org/doku.php#mingw-w64)
* [Git](https://git-scm.com)
* [Atom](https://atom.io)
* [Ruby-lang](https://rubyinstaller.org)
* [RubyGems](https://rubygems.org)
* [Jekyll](https://jekyllrb.com)

***

## Sommaire :
### [Avant toutes choses ...](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Fork-Windows#avant-toutes-choses--1)
### [I. _Chocolatey_](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Fork-Windows#i-chocolatey-1)
#### [a. Installation de _Chocolatey_](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Fork-Windows#a-installation-de-chocolatey-1)
#### [b. Installation de _Chocolatey GUI_](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Fork-Windows#b-installation-de-chocolatey-gui-1)
### [II. _IDE_ et dépendances](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Fork-Windows#ii-ide-et-d%C3%A9pendances-1)
#### [c. Environnement de travail](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Fork-Windows#c-environnement-de-travail-1)
##### [Installation de Atom](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Fork-Windows#installation-de-atom-1)
##### [Installation de MinGW-w64](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Fork-Windows#installation-de-mingw-w64-1)
##### [Installation de Git](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Fork-Windows#installation-de-git-1)
#### [d. Dépendances JamStatick](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Fork-Windows#d-d%C3%A9pendances-jamstatick-1)
### [III. Clonage du dépôt de projet](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Fork-Windows#iii-clonage-du-d%C3%A9p%C3%B4t-de-projet-1)

***

### [Avant toutes choses ...](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Fork-Windows#sommaire-)

>Imaginez que vous soyez la proie de vils raptors et autres sauriens des Temps Perdus, enfermé dans un parc zoologique avec des failles de sécurité importante (la faute à un.e administrateur.ice négligent.e) et que, face au poste de contrôle du système de gestion du lieu, vous soyez la seule personne capable de remettre les compteurs en place afin de pouvoir sauver vos amis et votre famille d'une mort certaine, que serait votre première réaction ?

***

![image](https://19yw4b240vb03ws8qm25h366-wpengine.netdna-ssl.com/wp-content/uploads/This-is-a-Unix-system-I-know-this.png)

***

>Bref, c'est important de tâter de la ligne de commande, ce truc affreux avec du texte blanc sur un fond noir ... C'est ce que nous allons utiliser pour cloner ce projet, vous allez voir que ça va nous faciliter la vie par la suite.

***

> Avant toute chose, il semble nécessaire de rappeler que Windows constitue un cas particulier dans cette série de tutoriels de par ses caractéristiques : il n'intègre pas les commandes usuelles UNIX de base, il sera nécessaire de palier à cet inconvénient en premier lieu afin de travailler dans les meilleurs conditions.

***

Vous aurez besoin d'utiliser l'outil [Windows Powershell](https://fr.wikipedia.org/wiki/Windows_PowerShell).

Pour ouvrir le programme, appuyez sur le bouton Démarrer de votre clavier puis entrez la recherche correspondante.

***

![image](https://lecrabeinfo.net/app/uploads/2020/04/ouvrir-powershell-windows-10-menu-demarrer-5e8af9b1b8f85.jpg)

![image](https://evotec.xyz/wp-content/uploads/2019/02/img_5c6c7909c2afc.png)

![image](https://asset.conrad.com/media10/isa/160267/c1/-/fr/002180367PI00/image.jpg)

***

Il est maintenant temps de se familiariser avec l'interface en ligne de commande :

```powershell
# |PS| désigne ici Powershell
# |C:\Users\'SESSION'| désigne le niveau de profondeur de la racine du système avec |'SESSION'| comme nom de session
# |>| indique qu'une commande est prête à être tapée.

Windows PowerShell
Copyright (C) Microsoft Corporation. Tous droits réservés.

Testez le nouveau système multiplateforme PowerShell https://aka.ms/pscore6

PS C:\Users\'SESSION'>

# 'pwd' indique le chemin du niveau de racine actuel

PS C:\Users\'SESSION'>pwd

Path
----
C:\Users\msi

# 'ls' indique l'ensemble des fichiers et dossiers la votre racine actuelle.

PS C:\Users\'SESSION'>ls

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-r---       05/12/2020     11:31                Desktop

# 'cd' permet de se déplacer à travers les dossiers de la racine

PS C:\Users\'SESSION'>cd Desktop

PS C:\Users\'SESSION'\Desktop>

PS C:\Users\'SESSION'\Desktop>cd ..

PS C:\Users\'SESSION'>

# Pour la suite, il sera nécessaire d'utiliser le Powershell en mode administrateur, recherchez le programme dans la barre de recherche comme précédemment décrit voir et clic-droit sur l'icône correspondante pour sélectionner 'Exécuter en mode administrateur'

PS C:\WINDOWS\System32>
```

***

> Pour des raisons de sécurité et pour éviter de compromettre le système, il ne faut jamais dupliquer ou écrire directement dans cette racine dossier, lorsque le système est amené à effectuer des actions qui modifie le dossier, notamment lors d'une installation, il faudra valider la fenêtre de _**contrôle de compte d'utilisateur**_ pour valider l'opération.

***

> Contrairement aux systèmes UNIX, Windows ne définit pas spécifiquement de niveau de privilège d'accès aux données, n'importe qui peut, muni du mot de passe de session, écrire, modifier, dupliquer ou supprimer des fichiers et dossiers, ce qui rend la gestion de la sécurité générale délicate.

***

> Pour éviter les intrusions malveillantes, Windows vérifie systématiquement qu'un logiciel possède une signature électronique qui atteste de sa conformité avec le système ; cependant, tout les programme ne le possèdent pas, notamment la plupart des projets multiplateforme de petite taille. Il est cependant possible de définir un script de [hachage cryptographique](https://fr.wikipedia.org/wiki/Md5sum) à exécuter dans le terminal.

***

### [I. _Chocolatey_](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Fork-Windows#sommaire-)

***

[Chocolatey](https://en.wikipedia.org/wiki/NuGet#Chocolatey) est un [gestionnaire de packages](https://fr.wikipedia.org/wiki/Gestionnaire_de_paquets) et un installateur de niveau machine en ligne de commande pour les logiciels Windows. Il utilise l'infrastructure de packaging **NuGet** et Windows **PowerShell** pour simplifier le processus de téléchargement et d'installation des logiciels.

Un paquet est une archive - _fichier compressé_ - comprenant les fichiers informatiques, les informations et procédures nécessaires à l'installation d'un logiciel sur un système d'exploitation au sein d'un _agrégat logiciel_, en s'assurant de la cohérence fonctionnelle du système ainsi modifié.

***

> C'est en effet au niveau de la racine `C:\WINDOWS\System32` où vont se placer les fichiers d'exécution des programmes qui seront référencés dans la base de données, il est donc important que leurs chemins d'accès soient correctement établis dès l'installation, d'où le choix d'un gestionnaire de paquet à la place d'un [assistant d'installation](https://fr.wikipedia.org/wiki/Assistant_(logiciel)).

***

![image](https://chocolatey.org/content/images/icon_slogan.png)

***

#### [a. Installation de _Chocolatey_](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Fork-Windows#sommaire-)

1. Tout d'abord, assurez-vous que vous utilisez un _[administrative shell](https://www.howtogeek.com/194041/how-to-open-the-command-prompt-as-administrator-in-windows-8.1/)_ - vous pouvez également installer en tant que non-administrateur, consultez [Non-Administrative Installation](https://chocolatey.org/docs/installation#non-administrative-install).

2. Installer avec `powershell.exe`.

>**REMARQUE:** veuillez inspecter https://chocolatey.org/install.ps1 avant d'exécuter l'un de ces scripts pour garantir la sécurité. Nous savons déjà que c'est sûr, mais vous devez vérifier la sécurité et le contenu de _**tout**_ script d'Internet avec lequel vous n'êtes pas familier. Tous ces scripts téléchargent un script PowerShell distant et l'exécutent sur votre ordinateur. Nous prenons la sécurité très au sérieux.  [Learn more about our security protocols](https://chocolatey.org/security).

```powershell
# Avec PowerShell, vous devez vous assurer que 'Get-ExecutionPolicy' n'est pas restreint. Nous vous suggérons d'utiliser 'Bypass -Scope Process' pour contourner la politique pour installer les choses ou 'AllSigned' pour un peu plus de sécurité

PS C:\Users\'SESSION'>Set-ExecutionPolicy AllSigned

# Exécutez maintenant la commande suivante:

# Nous avons affaire ici à un script spécifique au terminal Powershell, cas particulier qui ne sera pas commenté pour ne pas complexifier l'affaire puisque les prochaines action feront spécifiquement appel à des interpréteurs de commande de type [Shell Unix](https://fr.wikipedia.org/wiki/Shell_Unix).

PS C:\Users\'SESSION'>Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
```

3. Attendez quelques secondes que la commande se termine.

4. Si vous ne voyez aucune erreur, vous êtes prêt à utiliser Chocolatey! Tapez `choco` ou `choco -?` maintenant, ou consultez [Getting Started](https://chocolatey.org/docs/getting-started) pour les instructions d'utilisation.

***

#### [b. Installation de _Chocolatey GUI_](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Fork-Windows#sommaire-)

***

Il est possible d'utiliser une interface graphique pour faciliter l'interaction avec les différents éléments du gestionnaire de paquet, néanmoins, cela n'enlève pas la nécessité de connaître les opérations en ligne de commande.

***

![image](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/_wiki/screenshots/choco_mainscreen.png)

***

```bash
# Pour installer Chocolatey GUI, exécutez la commande suivante à partir de la ligne de commande ou de PowerShell

C:\Users\'SESSION'>choco install chocolateygui
```

***

### [II. _IDE_ et dépendances](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Fork-Windows#sommaire-)

***

#### [c. Environnement de travail](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Fork-Windows#sommaire-)

Passons à l'installation des éléments qui constitueront l'environnement de développement du futur projet.

Selon votre profil, vous pouvez également faire ces opérations via _**PowerShell**_, les instructions suivantes vous étant données pour les deux situations.

Ouvrez le gestionnaire graphique _**Chocolatey GUI**_ puis cliquez sur `chocolatey` afin de consulter la base de donnée des dépôts via la barre de recherche en haut à gauche.

Entrez le nom du logiciel que vous souhaitez installer dans la barre de recherche puis cliquez sur celui correspondant et cliquez sur le bouton `installer`.

***

##### [Installation de Atom](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Fork-Windows#sommaire-)

***

[Atom](https://fr.wikipedia.org/wiki/Atom_(%C3%A9diteur_de_texte)) est un éditeur de texte mais surtout un _**environnement de développement intégré**_ - ou **IDE** - c'est à dire que le logiciel contient des modules qui lui permettent de gérer un grand nombre d'option dans le traitement de texte, tel que l'indexation des commandes de langage ou l'interprétation des _brackets_ - c'est à dire qu'il repère au sein d'un fichier texte les éléments qui permettent l'exécution du code.

Doté de nombreuses aides à la lecture et à l'écriture, le logiciel est également extensible via de nombreuses extensions rassemblées dans un gestionnaire de paquet intégré.

![image](https://i.ytimg.com/vi/Y6PoRK0yBLg/maxresdefault.jpg)

![image](https://atom-ide-community.github.io/assets/images/screenshot-linter.png)

![image](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/_wiki/screenshots/choco_atom.png)

Pour installer _**Atom**_, exécutez la commande suivante à partir de l'_**Invité de Commande**_ ou du _**PowerShell**_:

```bash
# Pour installer Atom, exécutez la commande suivante à partir de l'Invité de Commande ou du PowerShell

C:\Users\'SESSION'>choco install atom
```

Si vous ne voyez aucune erreur, vous êtes prêt à utiliser Atom! Tapez `atom` ou `atom -v` avec l'_**Invité de Commande**_, ou consultez [Flight-Manual](https://flight-manual.atom.io/) pour les instructions d'utilisation.

***

> Le projet à forker est composé de nombreux fichiers reliés par un ensemble de dépendances qui en assurent la structure, la description des différents modules et leurs interactions sont décrits [ici](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Cha%C3%AEne-d'%C3%A9dition).

***

##### [Installation de MinGW-w64](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Fork-Windows#sommaire-)

[MinGW-w64](https://en.wikipedia.org/wiki/Mingw-w64) est une adaptation de l'environnement de développement du projet [GNU GCC](https://fr.wikipedia.org/wiki/GNU_Compiler_Collection) pour Windows et permet l'utilisation des fonctions de Linux sur ce système, dont les commandes UNIX usuels.

![image](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/_wiki/screenshots/choco_MinGW64.png)

Pour installer la bibliothèque _**MinGW-W64**_, exécutez la commande suivante à partir de l'_**Invité de Commande**_ ou _**PowerShell**_:

```bash
# Pour installer la bibliothèque MinGW-W64, exécutez la commande suivante à partir de l'Invité de Commande ou PowerShell

C:\Users\'SESSION'>choco install mingw
```

Si vous ne voyez aucune erreur, vérifiez que la bibliothèque est correctement installée en exécutant `gcc -v` ou `g++ -v` avec l'_**Invité de Commande**_, ou consultez [Documentation](http://mingw-w64.org/doku.php/documentation) pour les instructions d'utilisation.

***

> L'installation de Git ci-dessous permet également d'installer directement l'environnement GNU-GCC, cette étape est un commentaire pour décrire en détail les briques essentielles pour travailler sur notre projet.

***

##### [Installation de Git](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Fork-Windows#sommaire-)

***

> « je ne suis qu'un sale égocentrique, donc j'appelle tous mes projets d'après ma propre personne. D'abord Linux, puis _[Connard](https://www.wordreference.com/enfr/git)_. » _**Linus Torvalds, PC World**_

***

![image](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/_wiki/screenshots/choco_git_install.png)
![image](https://github.com/etxetxe/DNSEP_Report_EESI_2020/blob/master/_wiki/screenshots/choco_git.png)

Pour installer _**Git**_, exécutez les commande suivantes à partir de l'_**Invité de Commande**_ ou du _**PowerShell**_:

```bash
# Pour installer Git, exécutez les commande suivantes à partir de l'Invité de Commande ou du PowerShell

C:\Users\'SESSION'>choco install git
```
```bash
C:\Users\'SESSION'>choco install git.install
```

Si vous ne voyez aucune erreur, vous êtes prêt à utiliser Git! Tapez `git version` avec l'_**Invité de Commande**_, ou consultez [Documentation](https://git-scm.com/doc) pour les instructions d'utilisation.

Pour ouvrir le programme **Git Bash**, appuyez sur le bouton Démarrer de votre clavier puis entrez la recherche correspondante.

***

![image](https://i.stack.imgur.com/tBfID.png)

***

#### [d. Dépendances JamStatick](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Fork-Windows#sommaire-)

***

Avant toute chose, il convient de décrire brièvement le [flux de travail](https://fr.wikipedia.org/wiki/Workflow) sur le projet de notre site :

* l'objectif est de pouvoir mettre à jour régulièrement le site par l'ajout de nouveaux articles, leurs rédactions doivent se faire de manière claire et simple avec des redirections de liens pour le vocabulaire et les chapitre pour pouvoir les modifier à la volé.

* Le mémoire fait appel à des fonctionnalités dynamique en JavaScript pour rechercher un mot dans un moteur de recherche ou convertir du HTML en PDF.

La solution a été d'utiliser un [générateur de site statique](https://fr.wikipedia.org/wiki/Jekyll_(logiciel)) qui convertis des fichiers [Markdown](https://fr.wikipedia.org/wiki/Markdown) en [HTML](https://fr.wikipedia.org/wiki/Hypertext_Markup_Language) tout en intégrant des appels de fonctions dynamique en [front-end](https://fr.wikipedia.org/wiki/Frontal_(serveur)) sans avoir besoin d'utiliser une base de donnée en [back-end](https://fr.wikipedia.org/wiki/Backend).

Écrit en [Ruby](https://fr.wikipedia.org/wiki/Ruby), [Jekyll](https://fr.wikipedia.org/wiki/Jekyll_(logiciel)) est un logiciel qui permet de générer les fichiers de conversions, d'appel et de dépendance nécessaire pour modifier le site à la volée une fois uploadé. Ce type de [pipeline](https://fr.wikipedia.org/wiki/Tube_(informatique)) porte le nom de [Jamstack](https://jamstatic.fr/2019/02/07/c-est-quoi-la-jamstack/).

***

![image](https://jekyllrb.com/img/jekyll-og.png)

***

Bien que Windows ne soit pas une plate-forme officiellement prise en charge, il peut être utilisé pour exécuter _**Jekyll**_ avec les réglages appropriés.

Le moyen le plus simple d'installer _**Ruby**_ et _**Jekyll**_ consiste à utiliser [RubyInstaller](https://rubyinstaller.org/downloads/) pour Windows.

_**RubyInstaller**_ est un programme d'installation autonome basé sur Windows qui comprend le langage Ruby, un environnement d'exécution, une documentation importante, etc.

1. Téléchargez et installez une version de _**Ruby+Devkit**_ à partir de [RubyInstaller Downloads](https://rubyinstaller.org/downloads/). Utilisez les options par défaut pour l'installation.

2. Exécutez `ridk install` durant la dernière étape de l'assistant d'installation. Ceci est nécessaire pour installer des gemmes avec des extensions natives. Vous pouvez trouver des informations supplémentaires à ce sujet dans la [RubyInstaller Documentation](https://github.com/oneclick/rubyinstaller2#using-the-installer-on-a-target-system).

***

> Une _**Gem**_ est un paquet du dépôt _Rubygems_ qui permet d'ajouter de nouvelles fonctions à un programme possédant une dépendance _Ruby_. Les dépendances suivantes permettent d'installer le générateur de site statique _**Jekyll**_.

***

3. Ouvrez une nouvelle fenêtre d'invite de commande à partir du menu Démarrer, afin que les modifications apportées à la variable d'environnement `PATH` deviennent effectives.

```bash
# Installez Jekyll et Bundler

C:\Users\'SESSION'>gem install jekyll bundler
```

4. Vérifiez si Jekyll a été correctement installé: `jekyll -v`.

Voilà, vous êtes prêt à utiliser Jekyll!

***

### [III. Clonage du dépôt de projet](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Fork-Windows#sommaire-)

![image](https://miro.medium.com/max/882/1*n5MnDrinAXeY2NpCX9H8cw.jpeg)

Avant toute chose, il convient de rappeler que, malgré leurs affinités et la manière dont ils sont amenés à être utilisé, ces deux logiciels restent utilisable de manière indépendante :

* [_**Git**_](https://fr.wikipedia.org/wiki/Git) est un logiciel libre, open-source, en local et décentralisé de _versioning_ c'est à dire que tout le monde héberge sa propre instance de fichiers ou de programme source, qui signifie en informatique une réplique d'un ensemble d'éléments de base, il est ainsi possible de travailler sur une version propre d'une instance et d'en partager les sources sans impacter les versions des autres développeurs et développeuses.
* [_**GitHub**_](https://github.com/) est un ensemble de services comprenant un système de dépôt au sein d'une base de données référencée, un gestionnaire et éditeur de fichier sous forme d'application web et bien d'autres, basé sur Git mais sous forme d'un système centralisé ou les développeurs travaillent et uploadent leurs instances modifiées sur le même dépôt.

Exécutons _**Git Bash**_ pour pouvoir commencer à utiliser les commandes _UNIX_ sur _Windows_.

Pour ouvrir le programme, appuyez sur le bouton Démarrer de votre clavier puis entrez la recherche correspondante.

```bash
# Par défaut le terminal s'ouvre à la racine du disque sur lequel le système d'exploitation est installé.

'SESSION'@'NOM_ORDI' MINGW64 ~
$

# On va supposer que l'on souhaite travailler à la racine du disque système au sein du répertoire 'Documents' dans l'arborescence de fichiers

'SESSION'@'NOM_ORDI' MINGW64 ~
$ cd Documents && git clone https://github.com/etxetxe/DNSEP_Report_EESI_2020.git && cd DNSEP_Report_EESI_2020 && git commit -m "Start" && git status

# Cette commande permet de se déplacer sur le répertoire 'Documents' puis d'utiliser la fonction 'clone' de git pour récupérer une copie du dépôt de fichiers à l'adresse indiqué pour l'installer au niveau du répertoire actuel 'Documents' puis de créer une nouvelle instance appelé 'Start' avant d'avant d'afficher un 'status' ou un rapport du dépôt enregistré en local

'SESSION'@'NOM_ORDI' MINGW64 ~/Documents/DNSEP_Report_EESI_2020
$ bundle exec jekyll serve

# La commande suivante permet d'exécuter sur un port réseau local à l'adresse 'localhost:4000' un déploiement du site généré.
```

Ouvrez votre navigateur favoris et entrez l'url : `localhost:4000`. Si votre navigateur affiche fièrement le site, vous avez passé avec succès la phase de fork !

Vous êtes maintenant prêt à développer sur votre nouveau projet ! Exécutez `atom .` pour débuter sur l'éditeur de code _**Atom**_.
