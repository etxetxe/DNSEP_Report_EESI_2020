En 2016 le département numérique de Getty Publications, la maison d'édition du musée américain The Getty, a mis en place une chaîne de publication numérique originale nommée "Quire", qui repose sur un générateur de site statique.
L'originalité de cette initiative dans un paysage éditorial relativement classique est une des motivations de ce projet {% cite evan_lan_editors_2016 %}, avant tout pensé pour permettre une pérennité et une maintenabilité des versions numériques, et offrir une meilleure expérience de lecture numérique.
En creux apparaît l'interrogation suivante : comment concevoir et produire des livres autrement que par le biais de logiciels de traitement de texte et de publication assistée par ordinateur ?

## 2.2.1. Pérennité, résilience et qualité
Il y a plusieurs constats à l'origine de la mise en place de la chaîne de publication numérique de Getty Publications {% cite gardner_publier_2017 %}, constats qui peuvent être partagés par de nombreuses maisons d'édition.
Tout d'abord, et cela est d'autant plus vrai dans le domaine du patrimoine, les sources d'une publication numérique doivent être pérennes, ce qui comprend la consultation et l'exploitation des données pendant plusieurs années ou dizaines d'années.
Dans le même esprit, le système qui gère ces fichiers et qui produit les publications numériques doit être facilement maintenable.
Nous pouvons parler ici de résilience, en tant que faculté de résistance et d'adaptation de systèmes aux évolutions numériques – standards, formats, environnements informatiques.
Autre constat : une dépendance à des logiciels fermés, et dont l'évolution n'est pas contrôlée, peut se révéler critique.
Cette situation oblige ses utilisateurs à construire leur *workflow* sur des éléments contrôlés par d'autres.
Enfin, comme pour les livres imprimés, la qualité des publications numériques doit être une priorité.
Certains logiciels ne permettent pas des résultats satisfaisants en termes de design – nous pouvons évoquer l'export EPUB d'InDesign qui générait beaucoup d'erreurs il y a encore peu de temps, ou l'incapacité de ce logiciel de produire la version web d'un ouvrage.
Dans le cas de l'édition numérique, le recours à des outils comme des traitements de texte classiques ou des logiciels de PAO peut être contourné, mais encore faut-il trouver le bon outil, ou plutôt le bon processus : un ensemble de méthodes et une association de dispositifs.

## 2.2.2. Générateur de site statique
La brillante idée d'Eric Gardner de Getty Publications a été de détourner un outil déjà existant : un générateur de site statique {% cite gardner_building_2015 %}.
Un générateur de site statique présente plusieurs avantages par rapport aux systèmes classiques de gestion de contenu : il est conçu pour générer un ensemble de pages web organisées – des fichiers HTML, CSS et JavaScript – à partir de contenus décrits dans un langage de balisage léger comme Markdown, et de métadonnées indiquées dans ces mêmes pages ou dans des fichiers indépendants souvent au format YAML.
Tous les fichiers sont _à plat_ : il n'y a pas de base de données.
L'édition de contenus est simple, l'outil peut être facilement modifié, et la même source est utilisée pendant tout le processus – de l'écriture à l'édition jusqu'à la publication.
Un _static site generator_ est pensé comme un programme, et bien souvent géré de la même façon, avec un logiciel de gestion de versions.
Ce dernier offre la possibilité de travailler à plusieurs sur des fichiers texte – cela fonctionne donc autant avec du code que du texte.
Git est l'un des plus utilisé, démocratisé par la plate-forme GitHub.

Eric Gardner s'est servi de Middleman puis de Hugo, deux générateurs de site statique, pour gérer et produire des publications numériques et des ouvrages imprimés, avec pour objectif la résolution des trois contraintes présentées ci-dessus – pérennité des fichiers sources, indépendance du système, qualité des objets numériques.
La pérennité est permise par un système qui repose sur des standards et des formats ouverts : Markdown, YAML, HTML, CSS, Git.
Il existe de nombreux générateurs de site statique, leur code est open source, et il est relativement simple de changer d'outil, ou en tout cas cela est techniquement possible, il y a donc une forme d'indépendance.
Enfin, la qualité des productions ne dépend pas de l'outil mais de la façon dont il est configuré, avec un fonctionnement plus proche du webdesign que d'un logiciel propriétaire.
La production d'un site web, d'un fichier PDF et d'un livre numérique au format EPUB se fait avec un _workflow_ unique et à partir d'une même source.
Même si cette chaîne de publication s'inspire d'autres initiatives dont O'Reilly Media, il faut noter le caractère original et innovant d'une telle entreprise, d'autant plus dans un milieu comme l'édition, dans lequel le temps manque pour expérimenter et changer des habitudes bien ancrées.

## 2.2.3. Investissement et formation
Cette chaîne de publication présente un coût humain non négligeable : plusieurs mois de recherche et développement, et de formation pour les membres de l'équipe – notamment quelques jours pour apprendre à maîtriser le langage de balisage léger Markdown et le système de gestion de versions Git.
Le mouvement d'apprentissage est double : il s'agit autant d'apprendre de nouvelles méthodes que de _désapprendre_ le recours à des logiciels classiques.
Parce qu'InDesign intègre la pré-visualisation, chaque action sur les contenus ou sur la mise en forme est immédiatement visible, ce qui crée par ailleurs une confusion entre la structure et son rendu graphique.
Avec le _worflow_ de Getty Publications l'aperçu du rendu n'est pas forcément omniprésent, ce qui permet de se concentrer sur une opération qui ne concerne pas la mise en forme : les contenus.
Par ailleurs si l'édition de fichiers Markdown reste relativement simple, l'utilisation de Git requiert plus de temps, avec des subtilités parfois complexes qui nécessitent de l'accompagnement et de la pratique.
Intégrer une nouvelle approche des processus techniques d'édition, plus proche du développement web, est une action plus aisée si un designer-développeur fait partie de l'équipe, et c'est le cas pour le département numérique de Getty Publications.

Nous pourrions soumettre une limite à ce modèle basé sur un langage de balisage léger comme Markdown et sur le format YAML pour les métadonnées : le texte ne peut pas être structuré d'une façon aussi précise qu'avec le schéma XML TEI par exemple.
Il nous faudrait probablement définir, à partir du projet de chaîne de publication de Getty Publications, les cas d'usage qui semblent les plus appropriés ou recommandables.
Toutefois Markdown peut intégrer des éléments en HTML, ainsi ce langage de balisage léger très simple d'utilisation pourrait devenir beaucoup plus puissant en termes de description sémantique avec des compléments en HTML.

{% figure caption: "Figure 2.4. Capture d'écran d'une vidéo de démonstration du workflow de Getty Publications ([https://www.youtube.com/watch?v=VVYe0qR5DnM](https://www.youtube.com/watch?v=VVYe0qR5DnM))." %}
![Figure 2.4. Capture d'écran d'une vidéo de démonstration du workflow de Getty Publications (https://www.youtube.com/watch?v=VVYe0qR5DnM).]({{ "/images/2-getty-apercu-du-workflow.png" | absolute_url }})
{% endfigure %}

En comparaison, la maîtrise de Word, InDesign, ou tout autre logiciel de traitement de texte ou de publication assistée par ordinateur présente également un temps d'apprentissage relativement long, mais il s'agit rarement d'un investissement sur le long terme : savoir utiliser une UI – _user interface_ ou interface utilisateur – se limite souvent à une interface et non à une autre.
La pratique de langages de balisage léger ou la connaissance d'un système de versions peut être réutilisée dans d'autres situations, avec d'autres chaînes d'édition ou dans d'autres domaines : développement logiciel, développement web, systèmes complexes de traduction ou de révision avec plusieurs équipes, etc.

## 2.2.4. Prouesse technique
Cette chaîne de publication entend résoudre de nombreux défis : fluidifier les processus de conception et de production, faciliter l'intervention d'acteurs divers de la maison d'édition durant les différentes phases, rendre la chaîne maintenable dans le temps, ne pas dépendre de logiciels dont l'évolution est incertaine, et permettre une longévité en termes d'accès aux fichiers, avec des formats pérennes.
Plusieurs livres ont été créés de cette façon, ils sont consultables en ligne ou téléchargeables dans plusieurs formats ([http://www.getty.edu/publications/digital/digitalpubs.html](http://www.getty.edu/publications/digital/digitalpubs.html)).

{% figure caption: "Figure 2.5. Capture d'écran de la version web du livre Roman Mosaics ([http://www.getty.edu/publications/romanmosaics/](http://www.getty.edu/publications/romanmosaics/))." %}
![Figure 2.5. Capture d'écran de la version web du livre "Roman Mosaics" (http://www.getty.edu/publications/romanmosaics/).]({{ "/images/2-getty-roman-mosaics.png" | absolute_url }})
{% endfigure %}

Il est certain que la mise en place et la prise en main d'une telle chaîne de publication n'est pas à la portée de toutes les équipes, pour des raisons de temps : en développement, en adaptation, et en apprentissage.
Eric Gardner l'a signalé lui-même dans un entretien {% cite gardner_publier_2017 %}, certaines parties de cette chaîne de publication sont particulièrement élaborées.
Par exemple il faudrait utiliser et/ou créer des interfaces facilitant l'usage de Git, de la même façon que certains éditeurs de texte donnent un rendu de Markdown plus compréhensible que d'autres.
Un tel chantier pourrait par ailleurs être mutualisé entre maisons d'édition d'un même domaine éditorial.

D'autres structures d'édition, notamment dans le secteur du patrimoine culturel et artistique, pourraient adopter le même type de *workflow*.
Les questions de création de briques logiciels, de formations, de diffusion de documentations et de visibilité pourraient être développées à plusieurs, renforçant ainsi le concept d'une telle chaîne par différents modes d'application.
L'équipe de Getty Publications tente déjà de faire cela avec une description des outils et méthodes utilisés ([http://www.getty.edu/publications/digital/platforms-tools.html](http://www.getty.edu/publications/digital/platforms-tools.html)), des articles, des vidéos et des interventions.
Il faut noter que l'équipe du département numérique de Getty Publications réalise actuellement une documentation de Quire sur la plate-forme GitHub pour permettre sa diffusion ([https://github.com/gettypubs/quire](https://github.com/gettypubs/quire)).

Véritable progrès technique, cette chaîne de publication reste pour le moment une expérimentation isolée qui ouvre pourtant des perspectives nouvelles pour des secteurs comme celui de The Getty, le patrimoine culturel, mais probablement aussi pour de nombreux autres champs.
Alternative à des logiciels fermés et nouvelle méthode de collaboration éditoriale, cette chaîne de publication mérite d'être connue, expérimentée et diffusée.
Gilbert Simondon est un philosophe français né en 1924 et mort en 1989.
Philosophe de la technique, mais également professeur de psychologie et de physique, il a une démarche résolument encyclopédique.
*Du mode d'existence des objets techniques* {% cite simondon_du_2012 %} est sa thèse complémentaire qu'il soutient en 1958 et qui est publiée la même année, dans laquelle il aborde la condition des *objets techniques* au même titre que les objets sacrés ou les objets esthétiques, pour construire une *culture technique* comme mode de rapport au monde de l'homme.
Ce texte est probablement le plus connu du philosophe, même si une vingtaine d'ouvrages ont été publiés, souvent posthume, dont : *L'Individu et sa genèse physico-biologique*, *L'individuation psychique et collective*, *Sur la technique*, *Sur la psychologie*, ou *Sur la philosophie*.

Encore étudiée et citée aujourd'hui, l'œuvre de Gilbert Simondon a marqué notre époque et a influencé des penseurs comme Gilles Deleuze, de nombreux philosophes contemporains comme Bernard Stiegler ou Pierre-Damien Huyghe s'y réfèrent directement.
Gilbert Simondon est en quelque sorte un héritier de Marx {% cite noauthor_seminaire_2012 %}, et prolonge les pensées de Gaston Bachelard et Henri Bergson {% cite barthelemy_rencontre_2008 %}.
*Du mode d'existence des objets techniques*, ou MEOT, représente en soi une révolution philosophique du vingtième siècle, Gilbert Simondon s'opposant à la plupart des penseurs techniques – dont Martin Heidegger qui ne pense pas la technique à partir de la catégorie de l'objet {% cite portis-guerin_gilbert_2016 %}.

MEOT est composé de trois parties : la première est consacrée à l'objet technique sous l'angle de sa genèse et de son évolution ; la seconde partie se concentre sur le rapport de l'homme et de la technique, notamment en traitant des questions d'éducation, de formation et de progrès ; la troisième partie fonde la culture technique, base du rapport de l'homme au monde et à la nature.
Nous nous concentrons ici sur la première partie *Du mode d'existence des objets techniques*, elle ouvre des perspectives passionnantes pour évaluer certaines technologies numériques du vingt-et-unième siècle, et y porter un regard critique.

## 1.3.1. Une critique de la technique
La question de la technique est encore abordée d'une façon dichotomique lorsque Gilbert Simondon écrit cette thèse : soit considérée comme purement utilitariste, soit sacralisée ou rejetée, la technique est détachée de la culture.
La première partie *Du mode d'existence des objets techniques* traite de la question de l'objet technique afin de constituer, dans le reste de cet ouvrage, une culture technique comme nouveau socle du rapport de l'homme au monde.
L'aliénation du monde contemporain n'est pas due à la machine, mais à une mauvaise reconnaissance de la technique.
Notre civilisation est "mal technicienne" {% cite parent_gilbert_1968 %} : elle comprend mal la technique et ne se positionne pas de façon juste par rapport à elle.
Nous ne pouvons que réaffirmer ce que Gilbert Simondon exposait il y a plus de cinquante ans : la technique est mal perçue, et pour mieux la comprendre l'auteur *Du mode d'existence des objets techniques* nous invite à définir l'objet technique en tant qu'être et en tant qu'individu.
L'objet technique est la clé de cette nouvelle compréhension de la technique : il est doté d'une existence et d'une individualisation.
Par ailleurs son analyse nous permet de définir ce qu'est le progrès technique.

Comment repositionner l'homme et la machine ?
À travers un travail de définition et de genèse, Gilbert Simondon présente tout d'abord les conditions d'existence de l'objet technique dans le premier chapitre de la première partie : phénomène de concrétisation et mode d'évolution de l'objet technique.
La question de l'individualisation occupe le deuxième chapitre : concept de milieu associé et forme de l'évolution technique.
En déterminant le mode d'existence des objets techniques, Gilbert Simondon place les bases d'une culture technique qu'il développe dans les parties suivantes, que nous ne commentons pas ici.

Afin d'illustrer la pensée de cette première partie et de la replacer dans un contexte contemporain – un monde numérique –, nous nous attarderons sur un exemple d'objet technique qui nous intéresse particulièrement ici : les chaînes de publication, c'est-à-dire l'ensemble du processus de conception et de production de livres.
Enfin, nous répondrons à deux questions essentielles.
Comment dépasser une conception uniquement utilitariste de la technique, quelle peut être cette perfection interne des machines ?
Le progrès technique ne peut-il pas être autre chose qu'une recherche effrénée vers l'efficacité et émanciper l'homme de son mauvais positionnement par rapport à la machine ?

## 1.3.2. La génèse de l'objet technique
Dans le premier chapitre de la première partie *Du mode d'existence des objets techniques*, Gilbert Simondon cherche à décrire l'objet technique suivant son évolution : en cherchant les liens entre un objet technique du passé et un objet technique du présent, nous découvrons une ontogenèse.
Celle-ci s'appuie tout d'abord sur la définition du concept de "concrétisation" (p. 26), concept qui est l'une des conditions d'existence de l'objet technique.
Nous pouvons considérer que l'objet technique a une "forme abstraite" (p. 24) lorsqu'il est dissocié de son environnement de fonctionnement, à l'inverse la concrétisation de l'objet technique se définit par l'imbrication des fonctions qui le composent, celles-ci peuvent former une synergie : les fonctions convergent.

Prenons l'exemple de l'ustensile : en soit il ne fait que répondre à un besoin précis, il est purement fonctionnel, sa ou ses fonctions sont chacune indépendante, son fonctionnement est linéaire – une fonction après l'autre –, il s'agit d'un objet technique abstrait.
Prenons un second exemple : un moteur n'a pas un fonctionnement linéaire, ses éléments sont imbriqués, certaines fonctions se répondent entre elles, il y a une synergie interne au moteur, il s'agit d'un objet concret.
En termes de genèse l'"objet technique abstrait" (p. 29) est primitif, ancien, il y a donc une évolution technique, mais comment s'est-elle déroulée ?
Le progrès technique est brusque, il n'est pas continu, il est composé d'"évolutions mineures" (p. 46) et d'"évolutions majeures" (p. 46).
Les évolutions mineures sont des améliorations : ajout d'une fonction augmentant l'efficience de l'ensemble, comme le fait de compléter une phrase par un appendice entre parenthèses.
Les évolutions majeures s'appuient sur les évolutions mineures, elles se traduisent par de nouveaux objets techniques, comme le fait de reformuler une phrase pour la compléter, plutôt que de lui adjoindre une parenthèse : remplacer l'extension par une refonte.

Ce que nous pouvons en déduire, c'est que la perfection d'un objet technique ne correspond pas à son degré de résolution d'un problème, mais à la cohérence et la performance de son propre fonctionnement.
Nous ne devons pas tomber dans une recherche de l'utilité pure qui nous obligerait à juger d'un degré de progrès technique en fonction de la simple réponse de l'objet technique à un problème que nous aurions posé.
Il y a une forme de beauté interne de l'objet technique, que nous pourrions comparer à celle d'un organisme, même si un objet technique n'est pas vivant.
Si nous parlons ici d'évolution technique, quelle forme prend-elle ?
Le progrès technique est basé sur un double mouvement : les évolutions mineures, correctives, donnent lieu à des évolutions majeures, de nouveaux objets techniques ; il ne s'agit donc pas d'une genèse, mais d'une filiation ; les objets techniques sont liés entre eux et le progrès technique n'est pas une évolution continue, mais un processus discontinu dans lequel l'humain a un rôle clé.

La question soulevée à la fin de ce premier chapitre est la suivante : comment est permise cette évolution ?
Quel est ce cadre inventé par l'homme et qui donne lieu à une concrétisation ?

## 1.3.3. L'individualisation de l'objet technique
Le second chapitre de cette première partie débute par la définition de l'"hypertélie" (p. 61) de l'objet technique, qui est un phénomène de spécialisation qui le rend moins adaptable, et moins autonome.
L'hypertélie peut être de plusieurs ordres : spécialisation, division en vue d'une spécialisation, efficience en fonction de l'environnement extérieur.
La plurifonctionnalité des objets techniques n'est possible que sans spécialisation des deux premiers types, elle est toutefois rendue possible dans un certain milieu, le troisième milieu : ni l'objet technique seul, ni son contexte.
Il s'agit donc d'un équilibre entre deux milieux, permis par l'homme : le "milieu associé" (p. 70).

La particularité du milieu associé est qu'il est créé par l'objet technique et que ce milieu permet à l'objet technique d'exister : "Ce milieu à la fois technique et naturel peut être nommé milieu associé.
Il est ce par quoi l'être technique se conditionne lui-même dans son fonctionnement." {% cite simondon_du_2012 %}
Prévoir ce qui se passera dans une situation d'application – l'objet technique immergé dans un contexte particulier – est la condition permise par l'homme, un acte d'invention, nous pouvons considérer la "causalité récurrente" (p. 75) comme son expression visible.
Cette forme d'autonomie, et donc cette individualisation, s'exerce au niveau de l'individu technique, et non au niveau de l'ensemble technique, ce dernier en héritant néanmoins, comme pour la causalité récurrente.
Si Gilbert Simondon insiste sur ce point, nous pouvons noter que le caractère d'individualisation concerne l'individu technique et le niveau inférieur, l'élément technique, mais sans que ce dernier ne possède de milieu associé.
Les éléments techniques ont un caractère d'individualisation uniquement parce qu'ils composent l'individu technique.
Le passage de causalité se fait donc entre élément technique et individu technique, nous devons approfondir l'aspect temporel qu'implique ce passage et quelle différence il y a avec le vivant.

Dans le cas du vivant l'organe ne peut être détaché de l'ensemble, alors que l'élément technique peut être retiré de l'individu technique ; le vivant engendre à l'identique, alors que la technique produit.
Le "temps de relaxation" (p. 83) est l'une des distinctions entre le vivant et la technique : comme nous avons déjà pu le voir le progrès technique est discontinu, en dents de scie.
Gilbert Simondon introduit le concept de "production indirecte" (p. 88), que nous pouvons comprendre comme l'amélioration progressive qui donne lieu à des nouveaux objets techniques, c'est par le jeu de leurs imperfections que les objets techniques évoluent, contrairement aux êtres vivants qui, par leur perfection, engendrent des êtres identiques à eux.
Nous pourrions ajouter une précision aux propos de Gilbert Simondon : les êtres vivants évoluent dans un temps long, ils ne sont pas parfaitement identiques lorsqu'ils s'engendrent, alors que les objets techniques connaissent des bons d'évolution.

La machine et l'homme sont très différents : la machine porte les outils et les dirige, et l'homme règle et dirige la machine.
Le point commun entre la machine et l'homme réside dans la notion d'individu, qui peut être considérée comme l'auto-régulation, il y a l'idée d'un fonctionnement autonome.
Par exemple la machine-outil ne fait qu'utiliser des outils, alors que l'objet technique est plus indépendant ; Gilbert Simondon fait également la distinction entre technicien et artisan pour appuyer cette précision.
Partant du constat d'une part que les civilisations non-industrielles n'ont pas d'individu technique parce que c'est l'homme qui porte les outils, et d'autre part que les civilisations industrielles ont des individus techniques parce que l'homme devient celui qui permet l'auto-régulation des machines, nous devons alors nous interroger sur le niveau d'intervention de l'homme sur l'objet technique.
L'homme était un individu technique, il ne peut donc intervenir _dans_ l'individu technique, mais _au-dessous_ – l'élément technique – ou _au-dessus_ – l'ensemble technique.

Gilbert Simondon introduit la notion de "culture technique" et prévoit de l'expliciter dans les prochaines parties, en tant qu'elle permet de résoudre la confusion autour de l'individualisation de l'objet technique : il n'est pas humain, mais parce qu'il est individu l'homme croit que la machine a des propriétés humaines.
"Il est nécessaire que l'objet technique soit connu en lui-même pour que la relation de l'homme à la machine devienne stable et valide : d'où la nécessité d'une culture technique." {% cite simondon_du_2012 %}

La pensée de Gilbert Simondon peut être considérée comme novatrice, l'analyse de la première partie nous en révèle déjà plusieurs raisons.
Le statut d'objet technique est une nouvelle approche, contrairement à des courants de pensée moderne comme la philosophie de Martin Heidegger.
Autre opposition avec Martin Heidegger, la conception de la technique présentée dans MEOT n'est pas une dépossession supplémentaire de l'homme, pas plus qu'elle est une simple supériorité de l'homme sur la nature comme le soutient Nietzsche.
Parmi ses contemporains, nous pouvons noter la position de Jacques Ellul qui place dans la technique une dimension politique et morale, en tant qu'elle est la source de nouvelles aliénations, ce que réfute justement Gilbert Simondon.
Ce dernier a également influencé nombre d'auteurs, nous pouvons citer Bernard Stiegler qui a bâti un concept d'"individuation" et de "transindividuation" {% cite stiegler_chute_2006 %} à partir d'une critique de Gilbert Simondon, ou Pierre-Damien Huyghe qui y fait référence dans plusieurs de ses travaux.

## 1.3.4. Un objet technique contemporain : les chaînes de publication
Pour illustrer les idées, les concepts ainsi que la thèse que Gilbert Simondon présente dans la première partie de son livre, nous choisissons un objet technique contemporain : les chaînes de publication.

Une chaîne de publication est l'ensemble des outils et méthodes qui forment le processus de conception et de production des livres, ou plus globalement des *publications*.
Un exemple type est le couple traitement de texte et logiciel de publication assistée par ordinateur.
A contrario les chaînes de publication qui utilisent les technologies et les méthodes du développement web peuvent représenter un progrès technique par rapport aux chaînes de publication classiques.
Ces dernières utilisent des logiciels destinés à accomplir une tâche : d'un côté écrire du texte et éventuellement le structurer avec un traitement de texte, et de l'autre côté mettre en forme et produire un fichier permettant une impression papier avec un logiciel de publication assistée par ordinateur.
Majoritairement propriétaires et fermés, le code de ces logiciels n'est pas accessible, modifiable ou partageable, plaçant ceux qui conçoivent et fabriquent les livres dans une situation d'aliénation imposée.
Par exemple si un logiciel comme InDesign ne prend plus en charge GREP – système d'expressions régulières permettant de faciliter les remplacements en série –, alors l'éditeur qui l'utilise est obligé de trouver une autre solution, ou pire il perd un temps précieux.
Autre exemple : si l'interface d'un traitement de texte est complètement revue, son utilisateur ne peut pas la modifier, et doit se former à nouveau pour être en mesure de la comprendre et de la prendre en main.
Avec des logiciels ouverts, une possibilité de modification par la communauté existe : cela ne veut pas dire que chaque problème a sa solution, mais il y a une *possibilité*.

L'arrivée du livre numérique a obligé les éditeurs à modifier une partie de cette chaîne et son mode de fonctionnement : en détournant l'usage d'un logiciel de PAO, ou en faisant appel à un autre outil – un logiciel dédié à la production de livre numérique –, et en devant ouvrir au moins en partie le code source de ces livres.
L'environnement a donc changé, et la chaîne de publication a connu une correction mineure : elle a été perfectionnée par l'ajout d'un élément, et le mode de production n'a été modifié qu'en partie.
Une chaîne de publication qui abandonne le duo traitement de texte et logiciel de PAO, et qui se base sur des technologies et des méthodes de travail du web, est une évolution majeure, et ce pour plusieurs raisons : il ne s'agit plus de simples perfectionnements fonctionnels ou correctifs – par exemple pour produire un livre numérique au format EPUB –, mais une modification de l'ensemble des éléments pour parvenir à produire un livre en plusieurs formats, dont le format EPUB.

L'un de ses éléments est l'utilisation d'un langage de balisage léger comme Markdown pour écrire et structurer les contenus, cette utilisation ouvre plusieurs perspectives, et assure plusieurs fonctions elles-mêmes imbriquées : pouvoir se passer d'un logiciel spécifique comme un traitement de texte ; s'assurer que le fichier sera lisible dans plusieurs années ou dizaines d'années ; transformer facilement les fichiers dans un format structuré comme le HTML ; et disposer d'un format permettant de structurer un texte tout en étant lisible par un humain.
Une chaîne de publication inspirée du web n'est pas seulement un meilleur moyen de concevoir et produire des livres, ou simplement un système perfectionné, nous constatons que cette chaîne est surtout l'occasion pour celle ou celui qui l'utilise de mieux comprendre la technique et de s'y positionner plus justement.
Mieux comprendre implique une action de documentation qui accompagne l'usage, consciemment ou inconsciemment, et donc de constitution d'une culture technique telle que Gilbert Simondon l'a théorisée.
S'y positionner plus justement : non pas _dedans_ comme avec un logiciel qui fonctionne telle une boîte noire, mais _au-dessous_, dans la création et l'ajustement d'éléments et de briques techniques, et _au-dessus_, dans l'orchestration de l'ensemble technique que forme cette chaîne de publication.

## 1.3.5. Un regard critique sur le monde numérique
Gilbert Simondon nous a donné le matériel nécessaire pour que nous conservions un regard critique sur le monde numérique du vingt-et-unième siècle – bien que *Du mode d'existence des objets techniques* est illustré d'exemples mécaniques et électrotechniques du milieu du vingtième siècle –, et pour que nous puissions nous y placer d'une façon juste, sans nous aliéner.
Encore aujourd'hui, la technique est embrassée ou rejetée, nous observons majoritairement une dualité entre postures technophile et technophobe, par manque de connaissance de la technique, mais également par manque de maîtrise de celle-ci.
En observant le fonctionnement même des machines et des systèmes techniques, et leur rapport avec leur environnement, nous pouvons intégrer la technique comme la possibilité d'établir une relation juste avec la nature.

Les chaînes de publication inspirées du web peuvent être considérées comme un objet technique ouvert et comme une occasion de mieux comprendre comment produire des livres : la culture technique est une question de réappropriation par des choix technologiques et des choix de processus.
Nous ne devons pas être naïfs quant au progrès technique que peut représenter cet exemple, celui-ci pouvant être repris au compte du fonctionnalisme ou de la recherche aveugle de l'efficacité.
Le progrès technique en tant qu'il peut être une émancipation de l'homme doit intégrer une dimension d'analyse et d'accompagnement continus : avoir le recul nécessaire sur les usages et les outils produits, et faire œuvre de pédagogie pour que ce recul puisse perdurer.

L'analyse de ce troisième texte majeur vient compléter un matériau théorique qui nous permet désormais d'aborder des exemples concrets de chaînes de publication originales, il s'agit de la partie suivante.
