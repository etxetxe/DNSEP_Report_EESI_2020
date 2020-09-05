# 3.2. Les principes d'un système modulaire de publication
Nous proposons ainsi d'abandonner le terme de "chaîne" au profit de celui de "système" : les étapes d'un processus de publication ne doivent plus être considérées comme une suite linéaire, mais comme un assemblage sophistiqué.
Cette proposition se base sur les constats mis en avant dans la partie précédente, notamment la confusion entre structure et mise en forme, le manque de compatibilité, la discontinuité des étapes ou la dépendance à certains logiciels.
Si les dix dernières années ont été consacrées à trouver des alternatives libres et ouvertes à des logiciels fermés et privateurs {référence nécessaire}, ce mouvement en faveur d'un remplacement peut, dans le domaine de l'édition – écriture, structuration, collaboration, composition – être dépassé.
Les projets portés par Getty Publications ou O'Reilly exposés dans la seconde partie illustrent ce mouvement : les traitement de texte et logiciel de publication assistée par ordinateur sont écartés au profit d'une nouvelle conception du processus de publication.
La notion même de "système" introduit le fait que les outils ne doivent pas remplir des fonctions les uns après les autres, selon un procédé linéaire, mais être assemblés d'une manière cohérente, afin de dialoguer entre eux.

L'association efficiente des outils qui constituent un _workflow_ d'édition requiert une circulation d'information entre eux.
Les questions de compatibilité adviennent assez vite lorsqu'il s'agit de communiquer entre les métiers qui composent la chaîne d'édition : de deux systèmes d'exploitation distincts et deux logiciels de traitement de texte dissemblables découlent au mois quatre sources de problèmes.
Les enjeux d'interopérabilité sont peut-être encore mal appréhendés dans le domaine de l'édition, nous tentons ici de trouver des solutions pertinentes.

Une dimension supplémentaire découle de l'interopérabilité des outils, celle de pouvoir les échanger à la manière de briques logicielles. {pas possible avec une approche WYSIWYG ?}
Cette dimension de modularité signifie que le système de publication est d'abord composé de fonctions, ces dernières sont remplies par des outils.
Le processus global n'est pas orienté par les outils, mais par les fonctions.

Nous l'avons déjà abordé, les formes du livre sont aujourd'hui principalement l'imprimé, le livre numérique homothétique et, en marge, le livre web.
Embrasser ces différentes possibilités, et être en capacité de générer facilement autant un PDF d'impression qu'une version web a des conséquences sur le système de publication.
Celui-ci ne doit plus être orienté pour l'imprimé et gérer comme il peut d'autres formats plus exotiques, il doit être multiforme par défaut.

L'interopérabilité, la modularité et la multiformité : trois principes qui soutiennent un système de publication pour éditer des livres *avec* le numérique.
Ces trois principes sont interdépendants, et ne sont pas exsangues de problèmes ou de critiques.
Si ce _nouveau_ modèle était en capacité de résoudre toutes les difficultés présentées dans la partie précédente, il aurait déjà été adopté.
Nous devons donc être exigent quand à la présentation de ces trois fondements, et extraire les nouvelles contraintes imposées par ce modèle.

## 3.2.1. Interopérabilité
La continuité, dans une chaîne de publication, est la capacité à passer d'une étape à une autre et donc d'un outil à un autre, facilement.
Pourquoi est-ce que cette continuité, sans friction, est nécessaire ?
Pour deux raisons que nous souhaitons exposer avec le plus de clarté possible, et qui illustre par ailleurs ce concept de "continuité".

L'étape de composition crée une tension dans le processus d'édition, en effet le logiciel utilisé pour la mise en forme ne peut pas être accessible à tous les intervenants du projet.
Par exemple lorsqu'un texte a été rédigé, relu et corrigé avec un traitement de texte par des auteur et correcteur, la composition est réalisée avec une autre application : un logiciel de publication assistée par ordinateur.
Ce dernier peut importer le fichier généré par le traitement de texte, et le designer graphique se charge alors de la mise en page du texte dans ce nouvel environnement informatique.
Si l'auteur souhaite intervenir à nouveau sur le texte pour intégrer des modifications, il rencontre une difficulté puisqu'il ne peut pas faire le chemin inverse, c'est-à-dire importer dans un traitement de texte le fichier produit par le logiciel de composition.
Deux solutions sont alors possibles : l'auteur dispose du même logiciel de mise en forme que le ou la graphiste – et le maîtrise –, ou il doit laisser une personne capable de réaliser cette action.
Le texte doit être fixé avant qu'une mise en forme puisse lui être attribué, il y a donc, à ce moment du processus, une rupture.

Deuxièmement, les formats des fichiers des traitements de texte et des logiciels de PAO, même s'ils sont désormais basés sur des standards XML, restent illisibles pour le commun des mortels.
La question de l'interopérabilité ne concerne pas que les programmes ou les machines, mais aussi les humains qui les manipulent.
L'utilisateur, pour lire un fichier issus de ces outils, doit forcément passer par ceux-là.
Ces fichiers sont comme des boîtes noires, difficile de savoir ce qu'ils contiennent hormis les informations que le logiciel compatible nous transmet.
Cela a une incidence sur la circulation et la gestion des fichiers.
Observons le fonctionnement adopté dans un autre domaine, le développement informatique.
Celui-ci n'est pas pris au hasard car il est également centré sur du texte, sauf qu'il s'agit cette fois de _code_.
Les projets sont un ensemble de fichiers organisés, chacun d'entre eux porte des informations lisibles avec un éditeur de texte, aucun logiciel particulier n'est nécessaire pour _lire_ le contenu – la question de l'interprétation est décorrélée.

Ainsi il est possible de _mettre à plat_ un projet, c'est-à-dire de le déconstruire en unités indépendantes et compréhensibles, même si les langages de programmation nécessitent des connaissances précises pour pouvoir être interprétés.
Cette mise à plat se traduit par l'association d'un système de contrôle de version pour manipuler – enregistrer, réviser, valider – les fichiers.
Git est actuellement le plus populaire dans ce secteur, offrant des fonctions puissantes de _versionnement_.
{définition de Git (Demaree, 2017) (Fauchié, 2018, MTL)}
{concept de convivialité (Illich, 2014)}
Il est intéressant de constater que Git est utilisé pour autre chose que du code, nous l'avons déjà vu avec la revue _Distill_ dans la seconde partie : les révisions sont versionnées, le code source des articles rendu public, etc.
Cette pratique est également en cours pour la gestion de textes techniques, notamment pour améliorer la collaboration autour de documents de travail au sein d'entreprises, c'est le cas pour les équipes marketing ou juridiques de GitLab (GitHub, 2018).

Pour contourner cette problématique de discontinuité liée aux formats et aux logiciels, plusieurs procédés existent, l'un d'eux est LaTeX.
LaTeX est l'association d'un langage de balisage, TeX, et d'un processeur qui génère différents formats à partir de cette source (Rouquette et al., 2012).
Créé par Leslie Lamport en 1983 à partir de TeX de Donald Knuth — lui-même créé en 1977 — LaTeX est pensé pour l'impression de documents — article, thèse, livre – et donc la production de fichiers PDF.
LaTeX est un système bien antérieur aux traitements de texte, et il repose sur les éléments suivants :

- un langage de balisage pour inscrire et structurer du texte : niveaux de titre, liste, notes de bas de page, pagination, italique, tableau, légendes, mais aussi des formules mathématiques ;
- l'édition des fichiers .tex se fait dans un éditeur de texte.
La syntaxe est compréhensible et plus légère que du HTML, en revanche la _lecture_ d'une source en .tex n'est pas chose aisée en raison des nombreuses balises ;
- la génération du format PDF se fait classiquement depuis un terminal, mais des logiciels avec des interfaces graphiques rendent cette génération plus simple ;
- dans la mesure où les fichiers .tex et associés — notamment pour gérer les bibliographies ou les feuilles de style — sont des fichiers texte, ils peuvent être ouverts et lus sur n'importe quel dispositif disposant d'un éditeur de texte sans risque de compromettre le fichier.

{illustration nécessaire}

LaTeX nécessite de disposer d'une infrastructure particulière pour générer les formats de sortie : elle peut comprendre des extensions destinées à la gestion des bibliographies ou des mises en forme spéciales, en plus d'une collection de programmes pour le fonctionnement général.
Cet ensemble est désigné sous le nom de "distribution LaTeX", tant il s'agit d'un mini-système d'exploitation typographique.
LaTeX a été conçu pour composer très habilement la typographie du document, jusqu'au dessin de caractères avec Metafont (Vallance, 2015).
Si LaTeX est stable et puissant, offrant la possibilité d'une structuration et d'une mise en forme très maîtrisées, idéale pour l'édition scientifique (Guichard, 2008), son utilisation demande un apprentissage important, certaines fonctionnalités sont complexes à manipuler – même avec des logiciels qui en facilitent la compréhension.
Par ailleurs, si le rendu pour l'impression est irréprochable il est néanmoins limité, les modèles et feuilles de style nécessitent des compétences importantes.
En fin, ce n'est pas un procédé pensé pour la génération de formes numériques – même si cela est possible, notamment du format HTML.
LaTeX est une approche programmatique pour concevoir et produire une publication _figée_, et ce système remplit parfaitement cette fonction.

Entre d'un côté la complexité des formats des traitements de texte et de l'autre la difficulté d'usage de LaTeX et son manque de multiformité, nous pouvons trouver une alternative qui répond à plusieurs prérogatives.
Ce dont nous avons besoin, c'est d'un moyen d'inscrire et de structurer du texte pour pouvoir en générer des formes diverses, tout en ayant la possibilité de voir et de comprendre la structure du document.
Le mode WYSIWYM, abordé dans la partie 3.1.1., répond à ces exigences : la qualification des contenus est prioritaire sur l'aperçu graphique qui en est donné.
Les langages à balisage léger sont l'application du mode WYSIWYM, le plus célèbre et répandu d'entre eux est Markdown.
"Un langage de balisage n’est rien d’autre qu’un système d’annotation d’un document qui s’effectue d’une telle manière qu’il est possible de distinguer ces balises, ces annotations, du texte que l’on annote." (Dehut, 2018)
Markdown a été inventé pour pouvoir écrire facilement en HTML, sans écrire en HTML : quelques balises permettent de structurer du texte, et sont facilement interprétables par différents outils ou processeurs.

{illustration nécessaire}

La _répartition_ de Markdown est telle que ce langage peut être considéré comme la norme de l'écriture numérique (Fauchié, s. d.).
Étant convertissable en HTML très facilement, ce format peut devenir la source utilisée tout au long d'un processus de publication.
Quire, le système de publication numérique de Getty Publications présenté dans la seconde partie, emploie Markdown.
La question principale reste la génération d'un format PDF pour l'impression, et c'est justement le format HTML, ou une version XML proche, qui peut être la base de cette version imprimable.
Une solution logicielle, propriétaire, assure cette conversion du format HTML vers un PDF de grande qualité, et c'est d'ailleurs le choix des systèmes Quire et Electric Books (Attwell, 2018).
PrinceXML est un programme fermé et propriétaire, et relativement coûteux.
Des initiatives diverses se sont constituées pour proposer des alternatives plus ouvertes, il s'agit d'un champ de recherche très actif.
À la suite d'HTML2print (OSP, 2017) ou de Vivliostyle (Taquet, 2017), Paged Media se consacre depuis 2017 à cette quête de l'impression d'une source HTML, publiant ses premiers résultats et organisant des temps d'échange autour de ces questions techniques et graphiques (Blanc, 2018).
Il serait en effet dommage de passer d'une hégémonie – le logiciel de publication assistée par ordinateur Adobe InDesign – à une autre – PrinceXML.

{Conclusion : lisibilité, interopérabilité, versionnement, Markdown, et exemples des 3 chaînes}

## 3.2.2. Modularité
L'interopérabilité ouvre la possibilité de ne pas dépendre d'un logiciel précis, et donc d'envisager une chaîne modulaire : chaque fonctionnalité est une brique à laquelle un ou des outils peuvent être attribués.
Expliquer ce qu'est la "non modularité". {référence nécessaire}
Présenter des exemples de chaînes modulaires, Métope par exemple (Muller, 2016), et ses limites. Pourquoi ne pas s'arrêter là ? Problème des systèmes d'import/export (rupture) {référence nécessaire}
Concept de la modularité sous l'angle de Simondon. Et Gelgon ! {Gelgon, 2018}
Image de la modularité : lego... Et exemples issus du développement web. {référence nécessaire}
Exemples de cas où la modularité présente tout son intérêt. (Gardner, 2017)
Limites de la modularité : création de nouvelles dépendances.

## 3.2.3. Multiforme
Grâce à une approche modulaire la chaîne de publication peut, potentiellement, générer de nouvelles formes ou de nouveaux formats.
Multiforme ? Retour sur le livre numérique, le livre web, l'impression à la demande. (Cramer, 2017)
Références à Salaün et Pédauque pour les nouvelles dimensions du document ?
Multiforme : aussi dans les sources consultables, exemples de Distill et de Getty (données qui peuvent être téléchargées). Dans certains contextes le livre ne se limite pas à l'objet seul (mais aux données qui vont avec)
Autre exemple avec Fire and Lion ?
Limite : impossible de prévoir ce qui va se passer, et donc d'anticiper sur de nouveaux formats, pourtant on peut espérer que cela suffise.

## 3.2.4. De nouvelles dépendances ?
Conclusion
Rappel des principes et leur articulation.
Est-ce que ce modèle ne risque pas de créer de nouvelles dépendances ?
Adoption de ce modèle : la question de l'accès (entretien Getty).
Finesse de la structuration : modèle limité à certains usages ? Un peu de diversité ne ferait pas de mal (et pas cette dualité Word/InDesign ou Métopes).
