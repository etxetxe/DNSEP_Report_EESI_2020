# Travailler depuis les sources : guide pas-à-pas

Ce guide vous explique comment créer un fork de mon projet de mémoire afin de pouvoir étudier son fonctionnement, soumettre des modifications et proposer une version alternative de ce dernier.

Emprunté au monde de la piraterie, un [fork](https://fr.wikipedia.org/wiki/Fork_(d%C3%A9veloppement_logiciel)) désigne une bifurcation au sein d'un projet afin de lui donner une nouvelle direction, de nouvelles entités indépendantes et autonomes sont crées mais conservent des similitudes avec le projet-mère.

***

> Pour des raisons de multiplicité des configurations sur Linux, je vais considérez que vous êtes déjà initié aux rudiments de la ligne de commande, vous pouvez vous référer à la page pour [OSX](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Fork-OSX) afin d'avoir une installation pas-à-pas.

***

## Méthode pour Linux

---

## Requis :
* _**Terminal**_ (celui que vous préférez)
* [Git](https://git-scm.com)
* [Ruby-lang](https://rubyinstaller.org)
* [RubyGems](https://rubygems.org)
* [Jekyll](https://jekyllrb.com)
* [Atom](https://atom.io)

***

## Sommaire :

### [Avant toutes choses ...](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Fork-Linux#avant-toutes-choses-)
### [I. IDE et dépendances](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Fork-Linux#i-ide-et-d%C3%A9pendances-1)
#### [a. Environnement de travail](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Fork-Linux#a-environnement-de-travail-1)
##### [Installation de Git](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Fork-Linux#installation-de-git-1)
##### [Installation de Atom](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Fork-Linux#installation-de-atom-1)
#### [b. Dépendances JamStatic](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Fork-Linux#b-d%C3%A9pendances-jamstatic-1)
### [II. Clonage du dépôt de projet](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Fork-Linux#ii-clonage-du-d%C3%A9p%C3%B4t-de-projet-1)

***

## [Avant toutes choses](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Fork-Linux#sommaire-)

***

>Imaginez que vous soyez la proie de vils raptors et autres sauriens des Temps Perdus, enfermé dans un parc zoologique avec des failles de sécurité importante (la faute à un.e administrateur.ice négligeant.e) et que vous étiez face au poste de contrôle du système de gestion du lieu, seul personne capable de remettre les compteurs en place afin de pouvoir sauver vos amis et votre famille d'une mort certaine, que serait votre première réaction face à la situation ?

***

![image](https://19yw4b240vb03ws8qm25h366-wpengine.netdna-ssl.com/wp-content/uploads/This-is-a-Unix-system-I-know-this.png)

***

>Bref, c'est important de tâter de la ligne de commande, ce truc affreux avec du texte blanc sur un fond noir ... C'est ce que nous allons utiliser pour cloner ce projet, vous allez voir que ça va nous faciliter la vie par la suite.

### [I. IDE et dépendances](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Fork-Linux#sommaire-)

***

#### [a. Environnement de travail](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Fork-Linux#sommaire-)

##### [Installation de Git](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Fork-Linux#sommaire-)

Il est plus simple d'installer Git sur Linux en utilisant le gestionnaire de packages préféré de votre distribution Linux. Si vous préférez construire à partir des sources, vous pouvez trouver des archives tar sur [kernel.org](https://www.kernel.org/pub/software/scm/git/) .

**Debian / Ubuntu**

Pour la dernière version stable de votre version de Debian / Ubuntu :

* `apt-get install git`

Pour Ubuntu, ce PPA fournit la dernière version stable en amont de Git

* `add-apt-repository ppa:git-core/ppa`,`apt update`,`apt install git`

**Fedora**

* `yum install git` (jusqu'à Fedora 21)
* `dnf install git` (Fedora 22 et versions ultérieures)

**Gentoo**

* `emerge --ask --verbose dev-vcs/git`

**Arch Linux**

* `pacman -S git`

**openSUSE**

* `zypper install git`

**Mageia**

* `urpmi git`

**Nix / NixOS**

* `nix-env -i git`

**FreeBSD**

* `pkg install git`

**Solaris 9/10/11 ( OpenCSW )**

* `pkgutil -i git`

**Solaris 11 Express**

* `pkg install developer/versioning/git`

**OpenBSD**

* `pkg_add git`

**Alpin**

* `apk add git`

**Red Hat Enterprise Linux, Oracle Linux, CentOS, Scientific Linux, et al.**

RHEL et ses dérivés livrent généralement des versions plus anciennes de git. Vous pouvez télécharger une archive tar et construire à partir des sources, ou utiliser un référentiel tiers tel que le projet communautaire IUS pour obtenir une version plus récente de git.

**Slitaz**

* `tazpkg get-install git`

##### [Installation de Atom](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Fork-Linux#sommaire-)

Vous pouvez installer Atom sur Linux à l'aide du gestionnaire de packages de votre distribution en le configurant pour utiliser l'un de nos référentiels de packages officiels. Cela vous permettra également de mettre à jour Atom lorsque de nouvelles versions sont publiées.

**Debian et Ubuntu (deb / apt)**

Pour installer Atom sur Debian, Ubuntu ou des distributions associées, ajoutez notre
référentiel de paquets officiel à votre système en exécutant les commandes suivantes:

* `wget -qO - https://packagecloud.io/AtomEditor/atom/gpgkey | sudo apt-key add -`
* `sudo sh -c 'echo "deb [arch = amd64] https://packagecloud.io/AtomEditor/atom/any/ any main"> /etc/apt/sources.list.d/atom. list '`
* `sudo apt-get update`

Vous pouvez maintenant installer Atom en utilisant `apt-get`(ou `apt` sur Ubuntu):

* `sudo apt-get install atom`

Vous pouvez également télécharger le package Atom .deb et l'installer directement:

* `sudo dpkg -i atom-amd64.deb`

* `sudo apt-get -f install` (Installer les dépendances d'Atom s'il leur manque)

**Red Hat et CentOS (YUM) ou Fedora (DNF)**

Pour installer Atom sur CentOS, Oracle Linux, Red Hat Enterprise Linux, Scientific Linux, Fedora ou des distributions associées qui utilisent les gestionnaires de packages YUM ou DNF, ajoutez notre référentiel de packages officiel à votre système en exécutant les commandes suivantes:

* `sudo rpm --import https://packagecloud.io/AtomEditor/atom/gpgkey`
* `sudo sh -c 'echo -e "[Atom] \ nname = Atom Editor \ nbaseurl = https: //packagecloud.io/AtomEditor/atom/ el / 7 / \ $ basearch \ nenabled = 1 \ ngpgcheck = 0 \ nrepo_gpgcheck = 1 \ ngpgkey = https: //packagecloud.io/AtomEditor/atom/gpgkey "> /etc/yum.repos.d/atom.repo '`

Vous pouvez maintenant installer Atom en utilisant `dnf`(ou `yum` selon votre distribution):

* `sudo dnf install atom`

Vous pouvez également télécharger le package Atom .rpm et l'installer directement:

* `sudo yum install -y atom.x86_64.rpm` (Sur les distributions basées sur YUM)
* `sudo dnf install -y atom.x86_64.rpm` (Sur les distributions basées sur DNF)

**SUSE (zypp)**

Pour installer Atom sur openSUSE ou d'autres distributions qui utilisent le gestionnaire de packages Zypp, ajoutez notre référentiel de packages officiel à votre système en exécutant les commandes suivantes:

* `sudo sh -c 'echo -e "[Atom] \ nname = Atom Editor \ nbaseurl = https: //packagecloud.io/AtomEditor/atom/el/7/ \ $ basearch \ nenabled = 1 \ ntype = rpm-md \ ngpgcheck = 0 \ nrepo_gpgcheck = 1 \ ngpgkey = https: //packagecloud.io/AtomEditor/atom/gpgkey "> /etc/zypp/repos.d/atom.repo '`
* `sudo zypper --gpg-auto-import-keys refresh`

Vous pouvez maintenant installer Atom en utilisant `zypper`:

* `sudo zypper install atom`

Vous pouvez également télécharger le package Atom .rpm et l'installer directement:

* `sudo zypper in -y atom.x86_64.rpm`

#### [b. Dépendances JamStatic](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Fork-Linux#sommaire-)

Par défaut, le langage Ruby est installé sur les systèmes OSX, cependant il est nécessaire de faire une mise à jour afin de pouvoir installer les modules (appelés _**Gems**_) les plus récents via le gestionnaire de _**Ruby**_.

L'outil RVM est un outil entièrement dédié à la gestion des versions du langage Ruby sur votre ordinateur. Il s'agit en effet de l'acronyme de Ruby Version Manager.

1. Pour installer RVM, ouvrez votre terminal et exécutez la commande suivante :

* `curl -sSL https://get.rvm.io | bash -s stable`

2. Vous devrez ensuite redémarrer le terminal. La commande `rvm` sera alors disponible. La commande `rvm list known` va lister les différentes versions de Ruby. Lisez le résultat pour déterminer la version la plus récente et utilisez la commande `rvm install` suivi du numéro de version pour lancer l'installation :

* `rvm install ruby-2.6.1`

3. Vous pouvez vérifier que la dernière version de Ruby est bien prise en compte par votre système avec la commande `ruby -v`. Si jamais le numéro de version n'a pas changé, c'est que la plateforme Ruby n'a pas modifié le réglage qui indique la version à utiliser. Utilisez la commande suivante pour signaler à Ruby la nouvelle version :

* `rvm use ruby-2.6.1 --default`

4. Ouvrez une nouvelle fenêtre d'invite de commande à partir du menu Démarrer, afin que les modifications apportées à la variable d'environnement PATH deviennent effectives. Installez Jekyll et Bundler en utilisant `gem install jekyll bundler`

5. Vérifiez si Jekyll a été correctement installé: `jekyll -v`

Voilà, vous êtes prêt à utiliser Jekyll!

***

### [II. Clonage du dépôt de projet](https://github.com/etxetxe/DNSEP_Report_EESI_2020/wiki/Fork-Linux#sommaire-)

![image](https://miro.medium.com/max/882/1*n5MnDrinAXeY2NpCX9H8cw.jpeg)

Avant toute chose, il convient de rappeler que, malgré leurs affinités et la manière dont ils sont amenés à être utilisé, ces deux logiciels restent utilisable de manière indépendante :

* [_**Git**_](https://git-scm.com/) est un logiciel libre, open-source, en local et décentralisé de _versioning_ c'est à dire que tout le monde héberge sa propre instance de fichiers ou de programme source, il est ainsi possible de travailler sur une version propre d'une instance et d'en partager les sources sans impacter les versions des autres développeu.r.e.s
* [_**GitHub**_](https://github.com/) est un ensemble de services comprenant un système de dépôt au sein d'une base de donnée référencé, un gestionnaire et éditeur de fichier sous forme d'application web et bien d'autres, basé sur Git mais sous forme d'un système centralisé ou les développeurs travaillent et uploadent leurs instances modifiées sur le même dépôt.

Exécutons _**Git Bash**_, par défaut le terminal s'ouvre à la racine du disque sur lequel le système d'exploitation est installé. Pour plus d'information concernant les [commandes de base](http://devernay.free.fr/cours/unix/unixref.pdf).

On va supposer que l'on souhaite travailler à la racine du disque système au sein du répertoire `Documents` dans l'arborescence de fichiers :

1. Exécutez la commande `cd Documents && git clone https://github.com/etxetxe/DNSEP_Report_EESI_2020.git && cd DNSEP_Report_EESI_2020 && git commit -m "Start" && git status` puis `bundle exec jekyll serve`

2. Ouvrez votre navigateur favoris et entrez l'url : `localhost:4000`

3. Si votre navigateur affiche fièrement le site, vous avez passé avec succès la phase de fork !

Vous êtes maintenant prêt à développer sur votre nouveau projet ! Exécutez `atom .` pour débuter sur l'éditeur de code _**Atom**_.
