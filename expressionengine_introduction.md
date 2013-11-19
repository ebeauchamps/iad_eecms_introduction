# ExpressionEngine: Introduction

## ExpressionEngine

[ExpressionEngine](http://www.ellislab.com/expressionengine) est un CMS flexible développé par EllisLab et basé sur PHP et MySQL. ExpressionEngine est développé sur base d’un framework PHP open-source: [CodeIgniter](http://www.codeigniter.com) Ses fonctionnalités peuvent donc facilement être étendues à l’aide d’add-ons rédigés dans ce langage.

A mes yeux, les grands atouts d’ExpressionEngine sont:

- Le fait qu’il s’agit d’un produit basé sur des technologies open source mais payant et maintenu par une compagnie: ElliLab. Cela vous donne un interlocuteur unique en cas de problème et permet un développement continu du produit.
- Sa nature modulaire qui lui donne une grande flexibilité tout en restant simple d’utilisation. Ce CMS s’adapte à la nature et à la structure de vos données et de votre méthode de travail, et pas l’inverse.
- Une documentation complète et mise à jour, ainsi qu’une communauté de développeurs et d’utilisateurs des plus serviable et amicale.

Bref, si vous êtes développeur front-end, ExpressionEngine est un excellent CMS vous permettant de réaliser des sites complexes, même sans maîtrise de PHP ou de MySQL. Si êtes développeur, back-end, vous trouverez en ExpressionEngine et en CodeIgniter un framework puissant et extensible.

Si ExpressionEngine n’est pas encore très connu en Europe et en Belgique, il a cependant un [pedigré intéressant en terme de fonctionnalités](http://ellislab.com/expressionengine/features) et [des références de qualité](http://www.hopstudios.com/blog/the_largest_expressionengine_sites/).

## Definir et structurer vos Contenus

### Channels

Les [channels](http://ellislab.com/expressionengine/user-guide/modules/channel/index.html) occupent une place centrale dans le mode de fonctionnement d’ExpressionEngine et sont au coeur de sa flexibilité. La plus grande partie des contenus du site vont être définis et structurés dans des channels. ExpressionEngine permet de définir des types de contenus très différents sans aucun présupposé.

Si vous avez besoin d’une métaphore, pensez à vos channels comme à des tables dans une bases de données. Les channels sont les outils pricipaux à l’aide desquels vous allez organiser et structurer les informations de votre futur site.

**Exemples:** channel "news", channel "événements", channel "produits"

D’autre éléments vont venir se greffer sur ces channels pour définir plus précisément les éléments de contenu (entries) qui y sont stockés.

### Field Groups, Custom Fields et Field Types

ExpressionEngine vous permet de définir [des champs et des groupes de champs](http://ellislab.com/expressionengine/user-guide/modules/channel/custom_fields.html). Chacun de ces groupes de champs peut être associé à un ou plusieurs channels et défini la structure des éléments stockés par ceux-ci.

Ces groupes de champs peuvent contenir des champs de différents types (fichiers, dates, texte simples, zones de textes, liste de choix, cases à cocher, [relations](http://ellislab.com/expressionengine/user-guide/modules/channel/relationships.html), [grilles](http://ellislab.com/expressionengine/user-guide/modules/channel/grid.html), etc.)

Si les channels sont des tables dans une base de données, les champs sont les colonnes définissant le contenu de chacune des tables

Exemple: Pour un channel "évenements" on aura par exemple les champs suivants:

- Titre
- Date de début
- Date de Fin
- Résumé
- Description étendue
- URL du site de l’événement

ExpressionEngine permet nativement d’utiliser un nombre limité de type de champs. De nombreux add-ons gratuits et payants vous permettent de disposer d’un éventail plus large.

Moyennant une connaissance de base de PHP et à l’aide de la documentation fournie par EllisLab, [vous pouvez facilement créer de nouveaux types de champs](http://ellislab.com/expressionengine/user-guide/development/fieldtypes.html) adaptés aux besoins du projet.

### Status

Chaque entry dans un channel possède une structure bien précise, définie par les champs associés au channel. [Chaque entry possède également un statut](http://ellislab.com/expressionengine/user-guide/cp/admin/channels/statuses.html). Les statuts sont généralement utilisés pour déterminer le statut de publication d’un item donné (publié, non-publié, en révision, brouillon, etc.).

Par défaut, les channels sont associés à un groupe de statuts de base définissant seulement deux états: publié (open) et non-publié (closed). Vous pouvez soit ajouter des statuts à ce groupe, soit créer d’autres groupes de statuts que vous pourrez ensuite lier à un ou plusieurs channels.

### Catégories

Vous pouvez également [définir des groupes de catégories](http://ellislab.com/expressionengine/user-guide/cp/admin/channels/category_management.html) qui peuvent ensuite être liés à un ou plusieurs channels. Au sein de ces groupes, les catégories peuvent être hiérarchisées ou pas.

## Stocker vos fichiers

Via le [File Manager](http://ellislab.com/expressionengine/user-guide/cp/content/files/file_manager.html) ExpressionEngine vous offre également une solution pour stocker vos fichiers (PDF, images, fichiers videos, sons, etc.) ailleurs que dans vos channels et vos custom fields.

### Upload Preferences

Vous pouvez définir autant de dossiers ([File Upload Preferences](http://ellislab.com/expressionengine/user-guide/cp/content/files/file_upload_preferences.html)) que nécessaire sur votre serveur pour stocker vos fichiers. A nouveau, ExpressionEngine ne vous oblige pas à travailler d’une façon particulière. Vous pouvez choisir de classer vos fichiers par type, par channel ou de toute autre façon qui vous convienne.

Ces upload preferences vous permettent de classer vos fichiers à l’aide de dossiers. Elles vous permettent également d’introduire des restrictions quant aux caractéristiques des fichiers qui peuvent être uploadés dans ces dossiers (taille des images, poids des fichiers, type de fichiers, etc) et de gérer les permissions à l'aide des member groups.

Les channels et les custom field font ensuite référence aux fichiers stockés dans ces différents dossiers. Vous pouvez également travailler directement avec vos fichiers, sans passer par des channels ou des custom fields, en utilisant le file module et [les tags qui s’y rapportent](http://ellislab.com/expressionengine/user-guide/modules/file/file_tag.html).

### File manager

Le File Manager vous permet, comme son nom l’indique, de gérer vos différents fichiers et éventuellement de réaliser des opérations simples telles que le redimensionnement ou la rotation d’images.

## Member groups et Members: gérer vos permissions

ExpressionEngine vous permet de définir des groupes d’utilisateurs et d’associer des membres à ces groupes. Ces divers groupes d’utilisateurs vont vous permettre de contrôler, avec une grande granularité, les privilèges et permissions que vous accordez aux membres de ces groupes.

Vous pouvez, par exemple, moduler les accès à l’interface d’administration du site ou à certaines zones de ce dernier, donner ou non accès à certaines fonctionnalités, à certains add-ons, à certaines upload preferences etc.

Même si le système de membership d’ExpressionEngine est assez complet, il ne suit pas la même logique que les channels et les templates.

- Il n'est pas possible d'utiliser des custom fields pour définir les caractéristiques de vos profils utilisateurs.
- Les templates permettant de gérer les membres et les fonctionnalités qui y sont liées (login form, création et édition de profils utilisateurs, etc) ne fonctionnement pas comme les autres templates.

Par conséquent, si votre site repose sur des fonctionnalités nécessitant des comptes utilisateurs et des options de gestion de ces derniers, quelques add-ons vous simplifieront la vie.

- [User](http://www.solspace.com/software/detail/user/) (Solspace) vous permettra de gérer plus facilement vos membres et les templates y étant liés. A l’aide de cet add-on, mettre en place et intégrer un système de membership et de gestion des profils utilisateurs au sein de votre site est un jeu d’enfant.
- Si vous avez besoin pour vos fonctionnalités de membership de toute la flexibilité que vous offent les channels, les custom fields, et les templates [Zoo Visitor](http://ee-zoo.com/add-ons/visitor) (EE-Zoo), [Profile:Edit](http://mightybigrobot.com/products/detail/profile-edit) (Mighty Big Robot) et [Safecracker Registration](https://objectivehtml.com/safecracker-registration) (Objective HTML) vous seront utiles. Ces add-ons établissent un pont entre les profils utilisateurs oar défaut et un channel "spécial" stockant les profils des membres.

## Templates: afficher vos données

### Template groups et Templates

ExpressionEngine vous permet de définir des groupes de templates et des templates au sein de ceux-ci. Ces templates sont hybrides en ceci qu’ils contiennent à la fois du code HTML / CSS / Javascript / XML / etc. et des tags propres au langage de templating d’ExpressionEngine.

Ces templates vont définir la manière dont sont affichées les données que vous avez structurées précédemment.

### Types de templates

ExpressionEngine n'a pas de prégugés, si la plupart de vos templates seront sans doute des fichiers HTML, il est également possible de créer des templates JSON, RSS, XML, etc. pour afficher vos données.

### Structure des URLS

La structure des URL dans un site ExpressionEngine est par défaut définie par la forme suivante:

```
template_group/template/url_title
```

Les tags ci-après sont les plus utilisés pour créer des liens entre des pages dynamiques:

- `{path="template_group/template"}` créera un lien vers un template précis dans un template group
- `{url_title_path="template_group/template"}` créera un lien vers un template précis dans un template group en ajoutant l’url title de l’entry à la fin de l’URL. Utilisé pour les pages de détail affichant une entry

Attention, les templates d’index dans les divers template groups n’apparaissent pas dans les structure d’URL.

Expressionenigne fait passer toutes les requêtes http par un fichier index.php qui apparait donc dans toutes les URL. Le module Mod Rewrite et des fichiers .htaccess peuvent êtres utilisés pour retirer la mention de ce fichier des URL.

### Tags

ExpressionEngine possède de nombreux tags et paramètres vous permettant d’afficher vos données et de réaliser certains tests et traitement de celles-ci avant affichage. Nous nous contenterons ici d’examiner les plus utilisés: les entry loops et les structures de contrôle ou tags conditionnels.

#### Channel Entries loops

La tag pair channel entries est votre outil de travail principal lorsque vous codez des templates. Cette tag pair vous permet d’afficher les données stockées dans vos channels. De nombreux paramètres sont disponibles et vous permettent de cibler vos requêtes.

```
{exp:channel:entries channel="channel_short_name" disable="custom_fields|categories|category_fields|member_data|pagination|trackbacks" orderby="date" sort="desc" limit="10" dynamic="no"}
	{title}
{/exp:channel:entries}
```

- **Channel**: vous permet de sélectionner le channel que vous visez. Il est possible d’aller chercher des entries dans plusieurs channels channel=”news|events” ou encore de travailler par exclusion plutôt que par inclusion channel=”not news”.
- **Status**: paramètre permettant de choisir des entrées ayant un certain status: status="open", status="not closed", status="open|highlight"
- **Disable**: paramètre d’optimisation. Si vous n’avez pas besoin de quelque chose, spécifiez-le ici. Ce paramètre évite au système d’allouer des ressources à des tâches non nécessaires.
- **Orderby** et Sort: permettent de classer les entries selon certains critères: date de publication, titre, custom field, status, etc. et de les afficher en ordre croissant ou décroissant. Ces paramètres peuvent être chaînés: orderby=”title|date” sort=”asc|desc”
- **Limit**: limite le nombre d’entries affichées sur une page. ce paramètre est couplé à la pagination pour vous permettre d’afficher de longues listes sur plusieurs pages.
- **Dynamic**: par defaut, ExpressionEngine va tenter d’être intelligent de travailler d’après la structure de vos URLs. Si vous souhaitez qu’il ne le fasse pas, ce paramètre doit être mis à “no”.

#### Structure conditionelles et opérateurs

Si vous êtes familiers avec les structure de contrôle en programmation, vous verrez qu’ExpressionEngine vous en donne quelques unes pour gérer vos templates.

If simple

```
{if segment_1 == "pouet"}
	something
{/if}
```

If / else

```
{if count == "1"}
	something
{if:else}
	something else
{/if}
```

If / elseif

```
{if count == "1"}
	something
{if:elseif count == "2"}
	something else
{if:else}
	default
{/if}

{if segment_1 == "pouet"}
	something
{/if}
```

L’ordre dans lequel ExpressionEngine execute ses opération (parse order) et le type de conditionnels utilisés peuvent parfois poser problème. Il faut donc vous familiarisez avec le mode de fonctionnement d’ExpressionEngine en la matière. Voir à ce sujet une présentation détaillée par Lodewijk Schutte (Low).

Il existe des add-ons gratuits étendant les possibilités des structures conditionnelles de base et modifiant leur ordre de préséance dans l’exécution des operations par ExpressionEngine. Les plus connus et les plus utilisés sont dans doute [Switchee](http://devot-ee.com/add-ons/switchee) et [IfElse](http://devot-ee.com/add-ons/ifelse) développés par Mark Croxton.

#### URL segments

ExpressionEngine possède nativement des variables qui vous permettent de travailler avec des segments de vos URL, ce qui permet par exemple de modifier la structure par défaut des URL ou encore de réaliser des templates plus complexes, puisque ces variables peuvent être utilisées dans des tags ou dans des conditionnels.

Exemple: `{segment_1}`, `{segment_2}`, etc.

### Templates Avancés

Certains éléments de votre site ne vont pas naturellement trouver leur place dans des channels. Pour gérer ces éléments, ExpressionEngine vous offre trois types d’outils. Ceux-ci sont à utiliser en fonction de vos besoins:

- **Global variables**: éléments statiques ne devant pas faire appel au contenu de vos channels ni contenir de tags ExpressionEngine.
- **Snippets**: éléments dynamiques pouvant faire appel au contenu des channels ou qui peuvent contenir des tags ExpressionEngine
- **Embedded templates**: identique aux snippets hormis le fait que des variables peuvent être transmises depuis le template parent au template enfant et utilisées dans ce dernier. Peuvent être nativement utilisé comme des fichiers et des variables peuvent être passées.

Les Embedded templates utilisent plus de ressources que les snippets, qui eux-même en utilisent plus que les global variables. Il est donc important de choisir le bon outil pour le travail à réaliser.

#### Global Variables

Contiennent de petites informations comme des introductions ou des contenus isolés que vous souhaitez tout de même pouvoir mettre à jour facilement. Ne peuvent pas contenir de tags ExpressionEngine

`{gv_news_page_intro}`

#### Snippets

Eléments dynamiques pouvant faire appel au contenu des channels et pouvant donc contenir des tags ExpressionEngine.

Exemple: liste des trois dernière news publiées `{sn_my_snippet}`

#### Embedded templates

Certains templates peuvent être imbriqués dans d’autres templates: c’est ce que l’on appelle des embedded templates. Ces templates sont à utiliser lorsque des variables doivent être passées depuis le template parent et récupérées par le template enfant.

**Template parent**

```
{embed="template_group/template" my_parameter="{entry_id}"}

{embed="template_group/template" my_parameter="value"}
```

**Template enfant**

```
{if "{embed:my_parameter}" == "value"}

	{exp:channel:entries channel="{embed:channel_short_name}" disable="custom_fields|categories|category_fields|member_data|pagination|trackbacks" entry_id="{embed:my_entry_id}" limit="1" require_entry="yes" dynamic="no"}
		{title}
	{/exp:channel:entries}

{/if}
```

## Créer un portfolio et un blog

Comme exercice, nous allons créer un portfolio et un blog à l'aide d'ExpressionEngine.

### Installation

La première étpe consiste à installer le software en local sur votre machine. Personellement, je travaille sur mac et [MAMP](http://www.mamp.info/en/index.html) est une solution très facile d'utilisation pour créer et maintenir un environnment de dévelopement local.

Une fois un environnement de développement local créé et configuré, il suffit de télécharger ExpressionEngine et de suivre pas à pas les [instructions d'installation mises à disposition par EllisLab](http://ellislab.com/expressionengine/user-guide/installation/installation.html). Veillez aussi à suivre [les conseils de sécurité](http://ellislab.com/expressionengine/user-guide/installation/best_practices.html) une fois l'installation terminée.

Si le sujet de la sécurité vous intéresse, je ne peux que vous recommander [le petit guide de Mark Huot disponible sur Mijingo](http://mijingo.com/products/ebooklets/securing-expressionengine-2/).

### Etablir un plan

Avant de commencer à coder, il est important de créer un fichier de planning, généralement sous la forme d'un document texte. Ce document, [inspiré de celui utilisé par Newism / Leevi Graham](http://vimeo.com/13378574), spécifie tout ce que nous derons créer dans ExpressionEngine pour satisfaire les besoins du projet.

Voici un exemple de fichier de planning. Pour ma part, j'inclus généralement ce dernier dans mon repository git pour le site, il est donc disponible pour tout le monde.

Outre le plan, il est également ilmportant de suivre certaines conventions. Celles-ci vont vous permettre de gagner du temps et de clarifier une série de concepts pour les membres de votre équipe ou pour tout développeur devant travailler sur votre site par après.

Voici une liste non exhaustives des conventions que j'applique:

- Avoir un field group correspondant à chaque channel. Cela peut créer certaines répétitions mais c'est nettement plus clair pour tout le monde.
- Un seul status group par site. Ces status sont uniquement liés au workflow de publication
- Etablir et respecter une nomenclature:
	- Tout cutom field est préfixé par "cf", les global variables par "gv", les snippets par "sn", etc. Une telle nomenclature augmente grandement la lisibilité des templates
	- Tout custom field utilise un namespace correspondant au channel auquel il s'applique: "cf_work_img", "cf_blog_summary", "cf_blog_body", etc.
	
Vous trouverez un exemple de plan dans le repository.

### Configuration

Une fois le plan réalisé, passons à la configuration du système.

#### Supprimer index.php des URL avec .htaccess

Sur des serveurs UNIX / Apache, [EllisLab fourni une marche à suivre pour supprimer "index.php" des URLs de votre site](http://ellislab.com/expressionengine/user-guide/urls/remove_index.php.html). Celle-ci implique de créer un fichier .htaccess dans la racine de votre folder publique (htdocs).

#### Etapes pour gagner du temps

Lorsque vous mettez en place un site ExpressionEngine, il convient de faire les choses dans un certain ordre pour être efficace. Voici la procédure standard à suivre pour gagner du temps:

1. **Installer vos add-ons**: Certains add-ons interagissent avec les members, les fichiers et les channels. Il est donc préférable de les installer dès le début.

2. **Mettre en place vos Member Groups**: Vous devrez certainement utiliser ces member groups dans les étapes suivantes. Typiquement, vous aurez un groupe pour les super-admins (le client en est généralement exclu) et un groupe pour les administrateurs de contenu. Certains autres groupes peuvent également être créés dans le cadre de certains projets. Vous devrez revenir aux Member Groups par la suite, mais mettez déjà en place ce dont vous avez besoin.

3. **Configurer vos Upload Destinations**: les Member Groups sont déjà en place pour spécifier vos permissions.

4. **Configurer vos Category Groups et vos catégories initiales**: vous pourrez spécifier les permissions des member groups relatives aux catégories. Les File Upload Destinations pourront être utilisées pour les images des catégories.

5. **Configurer les Status Groups et les Status**: Les Member Groups sont déjà en place pour vous permettre d'assigner les permissions.

6. **Configurer les Custom Fields pour chaque Channel**: les File Upload Destinations et les add-ons de type Fieldtypes sont déjà en place. N'oubliez pas d'écrire vos instructions au fur et à mesure. 

7. **Configurer les Channels**: Vos Category Groups, Status Groups et Custom Fields sont déjà en place.

8. **Terminer la configuration des member groups**: vous pouvez maintenant revenir aux Member Groups et leur asiigner les permissions pour les Channels et Modules, ainsi que faire les dernier réglages.

### Création des templates

#### Homepage

#### Blog: archive et catégories

#### Blog: page de détail

#### Portfolio: list page

#### Portfolio: detail page

#### About: page unique avec le module de pages

## Pour aller plus loin

Ces quelques pages ne contiennent qu’une introduction à ExpressionEngine. Ce système offre bien d’autres possibilités que vous serez amenés à utiliser si vous aller plus loin qu’une simple introduction.

### Fichiers de configuration dynamiques

Lorsqu’on développe un site de manière professionnelle aujourd’hui, il est courant de devoir gérer différents environnements server pour un même site: développement, staging, production.

ExpressionEngine permet aux utilisateurs confirmés de configurer une installation sans forcément utiliser le control panel, en passant uniquement par un fichier de configuration. Cette approche offre un gain de temps notable et augmente également la flexibilité de votre installation en terme d’environnements serveurs.

Quelques astuces PHP permettent de rendre ce fichier de configuration dynamique et de passer rapidement d’un serveur à un autre sans devoir configurer l’ensemble des paramètres du site à chaque fois que l’on change de serveur.

Voici [quelques](http://jamieonsoftware.com/post/59689619654/getting-to-know-expressionengine-2s-config-file-part) [articles](http://jamieonsoftware.com/post/59689768301/getting-to-know-expressionengine-2s-config-file-part) [intéressants](http://jamieonsoftware.com/post/59690117179/getting-to-know-expressionengine-2s-config-file-part) détaillant [cette procédure](net.tutsplus.com/tutorials/php/apply-the-dry-principle-to-build-websites-with-expressionengine-2/), ainsi que [la liste des paramètres utilisables dans le cadre de ces fichiers de configuration](http://ellislab.com/expressionengine/user-guide/general/hidden_configuration_variables.html).

### Channel Form

[Chanel Form](http://ellislab.com/expressionengine/user-guide/modules/channel/channel_form/) permet de créer des formulaires pour éditer ou publier des entries sans passer par votre control panel, directement depuis le front-end de votre site.

Chennel form est compatible avec de nombreux custom fields parmi les plus populaires et vous permet de créer de véritables petites applications en ligne à l’aide d’ExpressionEngine.

### Add-ons

De nombreux add-ons gratuits ou payants vous permettent d’augmenter les capacités et la flexibilité d’ExpressionEngine.

#### Devot-ee

[Devot-ee](http://devot-ee.com/) répertorie aujourd’hui autour de 2000 add-ons pour ExpressionEngine.

La communcauté comporte pas mal de développeurs reconnus pour leur travail et offrant un support utilisateur de qualité: Solspace, EE garage (Leevi Graham), Pixelandtonic (Brandon Kelly & Brad Bell and Andris Ševčenko), Go to Low (Lodewijk Schutte), Mark Croxton, Mighty Big Robot, EE-Zoo, Dev Demon, etc.

#### Développer vos propres add-ons

Si vous souhaitez développer vous même vos propres add-ons, [EllisLab vous propose des instructions détaillés pour ce faire](http://ellislab.com/expressionengine/user-guide/development/).

ExpressionEngine étant développé sur base du framwork MVC open source qu’est [CodeIgniter](http://ellislab.com/codeigniter), les ressources de ce framework sont disponibles et vous permettent de développer des add-ons relativement complexes en en temps record.

## Resources

Les [screencasts de Mijingo consacrés à ExpressionEngine](http://mijingo.com/products/screencasts/learning-expressionengine-2-complete-series/) (Ryan Ierlan) sont une excellente manière de se lancer dans ExpressionEngine de façon didactique.

Si vous préférez quelques tutoriels en ligne pour vous lancer, Mike Boyink de Train-ee vous en propose [quelques-uns en accès gratuit sur son site](http://www.train-ee.com/courseware/free-tutorials). Les ressources payantes valent également la peine.

[Getting Started with ExpressionEngine 2](http://vimeo.com/41789424) par Ellislab

- [Devot-ee](http://devot-ee.com/): le site de référence en matière d’add-ons pour ExpressionEngine
- [Show-ee](http://www.show-ee.com/): un site sur lequel vous pourrez trouver de nombreux sites réalisés à l’aide d’ExpressionEngine
- [EE-Insider](http://eeinsider.com/): la référence en ce qui concerne les news de la communauté
- [Le blog officiel d’EllisLab](http://ellislab.com/blog): de nombreux articles sont consacrés à ExpressionEngine.
- [ExpressionEngine conference](http://www.expressionengineconference.com/): Les conférences annuelles consacrées à ExpressionEngine
- [Vidéos de certains talks à EECI](http://vimeo.com/whoooz) mises à votre disposition par Inspire Conférence et Robert Eerhart