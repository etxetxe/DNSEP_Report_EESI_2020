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
