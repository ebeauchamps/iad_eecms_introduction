# ExpressionEngine: Introduction

## ExpressionEngine

[ExpressionEngine](http://www.ellislab.com/expressionengine) est un CMS flexible développé par [EllisLab](http://www.ellislab.com/) et basé sur PHP et MySQL. ExpressionEngine est développé sur base d’un framework PHP open-source: [CodeIgniter](http://www.codeigniter.com) Ses fonctionnalités peuvent donc être étendues à l’aide d’add-ons rédigés dans ce langage.

A mes yeux, les grands atouts d’ExpressionEngine sont:

- Le fait qu’il s’agit d’un produit basé sur des technologies open source mais payant et maintenu par une compagnie: EllisLab. Cela vous donne un interlocuteur unique en cas de problème et permet un développement continu du produit.
- Sa nature modulaire qui lui donne une grande flexibilité tout en restant simple d’utilisation. Ce CMS s’adapte à la nature et à la structure de vos données et de votre méthode de travail, et pas l’inverse.
- Une documentation complète et mise à jour, ainsi qu’une communauté de développeurs et d’utilisateurs des plus serviable et amicale.

Bref, si vous êtes développeur front-end, ExpressionEngine est un excellent CMS vous permettant de réaliser des sites complexes, même sans maîtrise de PHP ou de MySQL. Si vous êtes développeur back-end, vous trouverez en CodeIgniter un framework puissant vous permettant d'étendre les possibilité d'ExpressionEngine.

Si ExpressionEngine n’est pas toujours très connu en Europe et en Belgique, il a cependant un [pedigré intéressant en terme de fonctionnalités](http://ellislab.com/expressionengine/features) et [des références de qualité](http://www.hopstudios.com/blog/the_largest_expressionengine_sites/).

## Definir et structurer vos Contenus

### Channels

Les [channels](http://ellislab.com/expressionengine/user-guide/modules/channel/index.html) occupent une place centrale dans le mode de fonctionnement d’ExpressionEngine et sont au coeur de sa flexibilité. La plupart des contenus du site vont être définis et structurés dans des channels. ExpressionEngine permet de définir des types de contenus très différents sans aucun présupposé.

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

Via le [File Manager](http://ellislab.com/expressionengine/user-guide/cp/content/files/file_manager.html) ExpressionEngine vous offre également une solution pour stocker vos fichiers (PDF, images, fichiers videos, sons, etc.).

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
- Si vous avez besoin pour vos fonctionnalités de membership de toute la flexibilité que vous offent les channels, les custom fields et les templates, [Zoo Visitor](http://ee-zoo.com/add-ons/visitor) (EE-Zoo), [Profile:Edit](http://mightybigrobot.com/products/detail/profile-edit) (Mighty Big Robot) et [Safecracker Registration](https://objectivehtml.com/safecracker-registration) (Objective HTML) vous seront utiles. Ces add-ons établissent un "pont" entre les profils utilisateurs oar défaut et un channel "spécial" stockant les profils des membres.

## Templates: afficher vos données

### Template groups et Templates

ExpressionEngine vous permet de définir des groupes de templates et des templates au sein de ceux-ci. Ces templates sont hybrides en ceci qu’ils contiennent à la fois du code HTML / CSS / Javascript / XML / etc. et des tags propres au langage de templating d’ExpressionEngine.

Ces templates vont définir la manière dont sont affichées les données que vous avez structurées précédemment.

### Types de templates

ExpressionEngine n'a pas de préjugés, si la plupart de vos templates seront sans doute des fichiers HTML, il est également possible de créer des templates JSON, RSS, XML, etc. pour afficher vos données.

### Structure des URLS

La structure des URL dans un site ExpressionEngine est par défaut définie par la forme suivante:

```
template_group/template/url_title
```

Les tags ci-après sont les plus utilisés pour créer des liens entre des pages dynamiques:

- `{path="template_group/template"}` créera un lien vers un template précis dans un template group
- `{url_title_path="template_group/template"}` créera un lien vers un template précis dans un template group en ajoutant l’`url_title` de l’entry à la fin de l’URL. Ce tag est utilisé pour créer un lien vers les pages de détail affichant une entry.

Attention, les templates d’index dans les divers template groups n’apparaissent pas dans les structures d’URL.

#### Supprimer index.php des URLs

Expressionenigne fait passer toutes les requêtes http par un fichier `index.php` qui apparait donc dans toutes les URL.

Le module Apache Mod Rewrite et des fichiers `.htaccess` peuvent êtres utilisés pour retirer la mention de ce fichier des URL. [Voici un guide détaillé par EllisLab](http://ellislab.com/expressionengine/user-guide/urls/remove_index.php.html).

#### Template routes

Les [templates routes](http://ellislab.com/expressionengine/user-guide/urls/template_routes.html), disponibles à partir de la version 2.8.0 permettent de passer outre cette configuration des URLs par défaut.

Chaque template peut ainsi se voir assigné une URL particulière. Ces URL peuvent également contenir des variables qui peuvent dès lors être utilisées dans vos templates, tout comme les variables de segments plus classiques.

Chaque route peut être composée de segments définis par des variables et dont la syntaxe peut être spécifiée à l'aide de règles simples ou d'expressions régulières.

### Tags / balises

ExpressionEngine possède de nombreux tags et paramètres vous permettant d’afficher vos données et de réaliser certains tests et traitement de celles-ci avant affichage. Nous nous contenterons ici d’examiner les plus utilisés: les entry loops et les structures de contrôle ou tags conditionnels.

#### Channel Entries loops

[La tag pair channel entries](http://ellislab.com/expressionengine/user-guide/modules/channel/channel_entries.html) est votre outil de travail principal lorsque vous codez des templates. Cette tag pair vous permet d’afficher les données stockées dans vos channels. De nombreux paramètres sont disponibles et vous permettent de cibler vos requêtes.

```
{exp:channel:entries channel="channel_short_name" disable="custom_fields|categories|category_fields|member_data|pagination|trackbacks" orderby="date" sort="desc" limit="10" dynamic="no"}
	{title}
{/exp:channel:entries}
```

- **Channel**: vous permet de sélectionner le channel que vous visez. Il est possible d’aller chercher des entries dans plusieurs channels channel=”news|events” ou encore de travailler par exclusion plutôt que par inclusion channel=”not news”.
- **Status**: paramètre permettant de choisir des entrées ayant un certain status: status="open", status="not closed", status="open|highlight"
- **Disable**: paramètre d’optimisation. Si vous n’avez pas besoin de quelque chose, spécifiez-le ici. Ce paramètre évite au système d’allouer des ressources à des tâches non nécessaires.
- **Orderby** et **Sort**: permettent de classer les entries selon certains critères: date de publication, titre, custom field, status, etc. et de les afficher en ordre croissant ou décroissant. Ces paramètres peuvent être chaînés: orderby=”title|date” sort=”asc|desc”
- **Limit**: limite le nombre d’entries affichées sur une page. ce paramètre est couplé à la [pagination](http://ellislab.com/expressionengine/user-guide/modules/channel/pagination_page.html) pour vous permettre d’afficher de longues listes sur plusieurs pages.
- **Dynamic**: par defaut, ExpressionEngine va tenter d’être intelligent et de travailler d’après la structure de vos URLs. Si vous souhaitez qu’il ne le fasse pas, ce paramètre doit être mis à “no”.

#### Structure conditionelles et opérateurs

Si vous connaissez les structure de contrôle en programmation, vous verrez qu’ExpressionEngine vous en donne quelques unes pour gérer vos templates.

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

L’ordre dans lequel ExpressionEngine execute ses opérations (parse order) et le type de conditionnels utilisés peuvent parfois poser problème. Il faut donc vous familiarisez avec le mode de fonctionnement d’ExpressionEngine en la matière. Voir à ce sujet un [PDF](http://loweblog.com/downloads/ee-parse-order.pdf) et une [présentation détaillée](https://speakerdeck.com/low/parse-order-pro) par Lodewijk Schutte (Low).

Il existe des add-ons gratuits étendant les possibilités des structures conditionnelles de base et modifiant leur ordre de préséance dans l’exécution des operations par ExpressionEngine. Les plus connus et les plus utilisés sont dans doute [Switchee](http://devot-ee.com/add-ons/switchee) et [IfElse](http://devot-ee.com/add-ons/ifelse) développés par Mark "the" Croxton.

#### URL segments

ExpressionEngine possède nativement des variables qui vous permettent de travailler avec des segments de vos URL, ce qui permet par exemple de modifier la structure par défaut des URL ou encore de réaliser des templates plus complexes, puisque ces variables peuvent être utilisées dans des tags ou dans des conditionnels.

Exemple: `{segment_1}`, `{segment_2}`, etc.

### Templates Avancés

Certains éléments de votre site ne vont pas naturellement trouver leur place dans des channels. Pour gérer ces éléments, ExpressionEngine vous offre trois types d’outils. Ceux-ci sont à utiliser en fonction de vos besoins:

- **Global variables**: éléments statiques ne devant pas faire appel au contenu de vos channels ni contenir de tags ExpressionEngine.
- **Snippets**: éléments dynamiques pouvant faire appel au contenu des channels ou qui peuvent contenir des tags ExpressionEngine
- **Embedded templates**: identique aux snippets hormis le fait que des variables peuvent être transmises depuis le template parent au template enfant et utilisées dans ce dernier. Peuvent être nativement utilisé comme des fichiers et des variables peuvent être passées.
- **Template Layouts**: disponibles nativement à partir de la version 2.8, les templates layouts sont une manière de créer de l'héritage de templates dans ExpressionEngine. Les templates layouts sont assez semblables aux embeds mais permettent d'en réduire le nombre et de passer d'un paradigme d'includes à un paradigme de template parent et enfants avec héritage.

Les Embedded templates utilisent plus de ressources que les snippets, qui eux-mêmes en utilisent plus que les global variables. Il est donc important de choisir le bon outil pour le travail à réaliser.

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

#### Template layouts

Comme dit plus haut, cette fonctionnalité permet de passer à un nouveau paradigme en terme de templating avec ExpressionEngine: l'héritage de templates.

Le concept est assez simple à comprendre. Nous avons un template "parent" dans lequel viennent se placer les templates "enfants". C'est l'inverse du paradigme d'embedded templates qui était le seul dont nous disposions avant la version 2.8.0.

Voici un exemple simple:

**Template parent:** (n'est jamais affiché directement)

```
<!DOCTYPE html>
<!--[if lt IE 7]><html class="no-js lt-ie9 lt-ie8 lt-ie7" lang="en"><![endif]-->
<!--[if IE 7]><html class="no-js lt-ie9 lt-ie8" lang="en"><![endif]-->
<!--[if IE 8]><html class="no-js lt-ie9" lang="en"><![endif]-->
<!--[if gt IE 8]><!--><html class="no-js" lang="en"><!--<![endif]-->
	<head>
		<meta charset="utf-8" />
		<title>My HTML Title</title>
		<meta name="description" content="My awesome description" />
		<meta name="viewport" content="width=device-width, initial-scale=1.0" />
	</head>
	<body>
		{layout:contents}
	</body>
</html>
```

**Template enfant** (appelle le template parent)

```
{layout="layouts/_page"}

<p>Hello World</p>
```

Le template enfant, servi par le CMS lorsque le navigateur l'affiche, va appeller le template parent et le contenu du template enfant va s'afficher en lieu et place du tag `{layout:contents}`

Bien entendu, cette technique n'est utile que si il est possible de passer des variables depuis le template enfant vers le template parent. Ces variables peuvent soit être passées via le tag `{layout}` lui même, soit via un tag `{layout:set}`. Cette dernière syntaxe offre bien plus de flexibilité et est à privilégier.

**Template enfant**

```
{layout="layouts/_page" htmlTitle="New HTML Title"}

<p>Hello World</p>
```

ou

```
{layout="layouts/_page"}
{layout:set name="htmlTitle" value="New HTML Title"}

<p>Hello World</p>
```

**Template parent:**

```
<!DOCTYPE html>
<!--[if lt IE 7]><html class="no-js lt-ie9 lt-ie8 lt-ie7" lang="en"><![endif]-->
<!--[if IE 7]><html class="no-js lt-ie9 lt-ie8" lang="en"><![endif]-->
<!--[if IE 8]><html class="no-js lt-ie9" lang="en"><![endif]-->
<!--[if gt IE 8]><!--><html class="no-js" lang="en"><!--<![endif]-->
	<head>
		<meta charset="utf-8" />
		<title>{if layout:htmlTitle != ""}{layout:htmlTitle}{if:else}Default title{/if}</title>
		<meta name="description" content="My description" />
		<meta name="viewport" content="width=device-width, initial-scale=1.0" />
	</head>
	<body>
		{layout:contents}
	</body>
</html>
```

Il est à noter que les valeurs passées ne sont pas limitées à des chaînes de caractères. Vous pouvez passer des blocs de code entiers.

```
{layout:set name="js"}
    <script src="/d3.js"></script>
    <script src="/awesome-visual.js"></script>
{/layout:set}
```

## Créer un portfolio et un blog

Comme exercice, nous allons créer un portfolio et un blog à l'aide d'ExpressionEngine.

### Installation

La première étpe consiste à installer le software en local sur votre machine. Personellement, je travaille sur mac et [MAMP](http://www.mamp.info/en/index.html) est une solution très facile d'utilisation pour créer et maintenir un environnment de dévelopement local.

Une fois un environnement de développement local créé et configuré, il suffit de télécharger ExpressionEngine et de suivre pas à pas les [instructions d'installation mises à disposition par EllisLab](http://ellislab.com/expressionengine/user-guide/installation/installation.html). Veillez aussi à suivre [les conseils de sécurité](http://ellislab.com/expressionengine/user-guide/installation/best_practices.html) une fois l'installation terminée.

Si le sujet de la sécurité vous intéresse, je ne peux que vous recommander [le petit guide de Mark Huot disponible sur Mijingo](http://mijingo.com/products/ebooklets/securing-expressionengine-2/).

### Etablir un plan

Avant de commencer à coder, il est important de créer un fichier de planning, généralement sous la forme d'un document texte. Ce document, [inspiré de celui utilisé par Newism / Leevi Graham](http://vimeo.com/13378574), spécifie tout ce que nous derons créer dans ExpressionEngine pour satisfaire les besoins du projet.

Pour ma part, j'inclus généralement ce dernier dans mon repository git pour le site, il est donc disponible pour tout le monde.

Outre le plan, il est également important de suivre certaines conventions. Celles-ci vont vous permettre de gagner du temps et de clarifier une série de concepts pour les membres de votre équipe ou pour tout développeur devant travailler sur votre site par après.

Voici une liste non exhaustives des conventions conseillées:

- Avoir un field group correspondant à chaque channel. Cela peut créer certaines répétitions mais c'est nettement plus clair pour tout le monde.
- Un seul status group par site dans la mesure du possible. Ces status sont uniquement liés au workflow de publication.
- Etablir et respecter une nomenclature:
	- Tout cutom field est préfixé par "cf", les global variables par "gv", les snippets par "sn", etc. Une telle nomenclature augmente grandement la lisibilité des templates
	- Tout custom field utilise un namespace correspondant au channel auquel il s'applique: "cf_work_img", "cf_blog_summary", "cf_blog_body", etc.
	
Vous trouverez un exemple de plan dans le repository de ce cours.

### Configuration

Une fois le plan réalisé, passons à la configuration du système.

#### Supprimer index.php des URL avec .htaccess

Sur des serveurs UNIX / Apache, [EllisLab fourni une marche à suivre pour supprimer "index.php" des URLs de votre site](http://ellislab.com/expressionengine/user-guide/urls/remove_index.php.html). Celle-ci implique de créer un fichier `.htaccess dans la racine de votre folder publique (htdocs).

#### Etapes pour gagner du temps

Lorsque vous mettez en place un site ExpressionEngine, il convient de faire les choses dans un certain ordre pour être efficace. Voici la procédure standard à suivre pour gagner du temps:

1. **Installer vos add-ons**: Certains add-ons interagissent avec les members, les fichiers et les channels. Il est donc préférable de les installer dès le début. Nous installerons [developer](http://devot-ee.com/add-ons/developer-acc) et [Quicksave](http://devot-ee.com/add-ons/quicksave).

2. **Mettre en place vos Member Groups**: Vous devrez certainement utiliser ces member groups dans les étapes suivantes. Typiquement, vous aurez un groupe pour les super-admins (le client en est généralement exclu) et un groupe pour les administrateurs de contenu. Certains autres groupes peuvent également être créés dans le cadre de certains projets. Vous devrez revenir aux Member Groups par la suite, mais mettez déjà en place ce dont vous avez besoin.

3. **Configurer vos Upload Destinations**: les Member Groups sont déjà en place pour spécifier vos permissions.

4. **Configurer vos Category Groups et vos catégories initiales**: vous pourrez spécifier les permissions des member groups relatives aux catégories. Les File Upload Destinations pourront être utilisées pour les images des catégories.

5. **Configurer les Status Groups et les Status**: Les Member Groups sont déjà en place pour vous permettre d'assigner les permissions.

6. **Configurer les Custom Fields pour chaque Channel**: les File Upload Destinations et les add-ons de type Fieldtypes sont déjà en place. N'oubliez pas d'écrire vos instructions au fur et à mesure. 

7. **Configurer les Channels**: Vos Category Groups, Status Groups et Custom Fields sont déjà en place.

8. **Terminer la configuration des member groups**: vous pouvez maintenant revenir aux Member Groups et leur assigner les permissions pour les Channels et Modules, ainsi que faire les derniers réglages.

### Création des templates

##### Embeds, snippets, layouts et global variables

**layouts/_page**

Nous allons ici travailler avec les template layouts, disponibles à partir de la version 2.8 d'ExpressionEngine. Nous aurons donc un layout "parent" contenant le header (et la navigation), ainsi que le footer du site.

Chaque template enfant définira les contenus de la page, ainsi que quelques variables utiles: contenu de la balise `<title>`, navigation courante, etc.

Auparavant, nous aurions été contraints de gérer le header et le footer à l'aide d'un embed (header) et d'un snippet (footer) inclus dans chaque template.

**global variables**

Nous utiliserons les global variables pour stocker tous les petits éléments du site qui doivent être facilement éditables mais ne trouvent pas naturellement leur place dans un channel (intriduction et liste des pages, code google analytics, etc).

[Low Variables](http://gotolow.com/addons/low-variables) vous permet de facilement donner accès à ces global variables à vos utilisateurs, de gérer les permissions d'accès de manière fine, de profiter des custom fields et même de modifier le parse order.

#### Homepage

Ce template contient simplement:

- Un titre et une introduction pour la page
- Une liste des 3 dernier blog posts
- Une liste des deux derniers travaux.

C'est une page assez simple à réaliser. Attention au paramètre `dynamic="no"` dans vos tags `{exp:channel:entries}`.

**Exercice**: créer le template pour la homepage.

#### Blog: page de liste

Outre un titre et une introduction, ce template contient une liste paginée des derniers posts, ainsi qu'une liste cliquable des catégories permettant de filtrer la liste des posts. Prévoir et tester une interface de pagination détaillée.

**Exercice**: créer le template de liste pour le blog.

#### Blog: page de détail

Ce template affiche l'ensemble des champs définis pour les entries de type blog. La seule "difficulté" dans cette page consiste à réaliser une redirection vers la page 404 si une entrée n'est pas trouvée.

**Exercice**: créer le template de détail pour les blogposts.

#### Work: list page

Outre un titre et une introduction, cette page contient une liste paginée des dernières entries. Prévoir et tester une interface de pagination détaillée.

**Exercice**: créer le template de liste pour le portefolio.

#### Work: detail page

Cette page contient l'ensemble des champs définis pour les entries de type work. La seule "difficulté" dans cette page consiste à réaliser une redirection vers la page 404 si une entrée n'est pas trouvée.

**Exercice**: créer le template de détail pour les travaux.

#### About: page unique avec le module de pages

Cette page nous permet d'utiliser [le module de pages natif d'ExpressionEngine](http://ellislab.com/expressionengine/user-guide/add-ons/pages/).

**Exercice**: créer le template de détail pour les pages.

#### RSS pour le blog

ExpressionEngine n'est pas limité à la création de fichier HTML. Nous verrons ici comment créer un template en XML respectant le standard RSS 2.0.

**Exercice**: créer le template de détail pour le RSS du blog.

## Pour aller plus loin

Ces quelques pages ne contiennent qu’une introduction à ExpressionEngine. Ce système offre bien d’autres possibilités que vous serez amenés à utiliser si vous allez plus loin qu’une simple introduction.

### Fichiers de configuration dynamiques

Lorsqu’on développe un site de manière professionnelle aujourd’hui, il est courant de devoir gérer différents environnements serveur pour un même site: développement, staging, production.

ExpressionEngine permet aux utilisateurs confirmés de configurer une installation sans forcément utiliser le control panel, en passant principalement par un fichier de configuration. Cette approche offre un gain de temps notable et augmente également la flexibilité de votre installation en terme d’environnements serveurs.

Quelques astuces PHP permettent de rendre ce fichier de configuration dynamique et de passer rapidement d’un serveur à un autre sans devoir configurer l’ensemble des paramètres du site à chaque fois que l’on change de serveur.

Voici [quelques](http://jamieonsoftware.com/post/59689619654/getting-to-know-expressionengine-2s-config-file-part) [articles](http://jamieonsoftware.com/post/59689768301/getting-to-know-expressionengine-2s-config-file-part) [intéressants](http://jamieonsoftware.com/post/59690117179/getting-to-know-expressionengine-2s-config-file-part) détaillant [cette procédure](net.tutsplus.com/tutorials/php/apply-the-dry-principle-to-build-websites-with-expressionengine-2/), ainsi que [la liste des paramètres utilisables dans le cadre de ces fichiers de configuration](http://ellislab.com/expressionengine/user-guide/general/hidden_configuration_variables.html).

### Relationships et Playa

ExpressionEngine dispose d'un [champ "relationships"](http://ellislab.com/expressionengine/user-guide/add-ons/channel/relationships.html) permettant d'établir facilement des relations one to one et one to many entre vos entries. 

**Exercice**: ajouter un champ relationship au blog permettant de sélectionner des articles liés pour chaque blogpost.

[Playa](http://docs.pixelandtonic.com/playa/) est un add-on créé par [Pixel & Tonic](https://pixelandtonic.com/), antérieur au champ relationship natif, et offrant d'avantage de fonctionnalités tout en proposant une interface utilisateurs qui est à mon sens plus agréable. Ces fonctionnalités et cette interface ont cependant un prix.

### Grid et Matrix

ExpressionEngine dispose également d'un champ "Grid" de type matriciel. Ce type de champ vous permet de créer des contenus qui peuvent se répéter au sein d'une seule entry. Une gallerie de photos ou un tableau de prix sont deux exemples simples.

**Exercice**: ajouter à la page de détail des travaux la possibilité d'avoir une gallerie de screenshots (0 à 5) permettant de présenter divers aspect de chaque travail.

[Matrix](http://docs.pixelandtonic.com/matrix/) est un add-on créé par [Pixel & Tonic](https://pixelandtonic.com/), antérieur au champ grid natif, et offrant d'avantage de fonctionnalités tout en proposant une interface utilisateurs qui est à mon sens plus agréable. Matrix est également compatible avec d'avantage de champs disponibles à travers des add-ons. Ces fonctionnalités et cette interface ont cependant un prix.

### Search et Low Search

ExpressionEngine intègre également es fonctionnaités de recherche basiques, vous permettant de créer un formulaire de recherche et des pages de résultats. Cependant, si vous cherchez la performance ou si vous avez besoin de focntionnalités plus avancées, [Low Search](http://devot-ee.com/add-ons/low-search) et [Super Search de Solspace](http://www.solspace.com/software/detail/super_search/) sont les options à considérer.

**Exercice**: ajouter un moteur de recherche simple (et une page de résultats) à la page d'archive du blog.

### Autres add-ons

#### Low variables: un véritable couteau suisse

Low Variables vous permet de gérer très efficacement les diverses parties de votre site ne se résumant pas à des pages ou à des channels. Cet add-on vous permet de disposer de global variables avancées: supports de custom fields, contrôle granulaire des permissions, contrôle du parsing stage, etc.

**Démonstration** low variables sur un site existant.

#### Stash: un autre niveau de templating

[Stash](https://github.com/croxton/Stash) est un add-on développé par Mark "the" Croxton qui permet de changer radicalement la manière dont vous codez vos templates avec ExpressionEngine.

C'est un add-on gratuit mais extrèmement puissant. Dans les mains d'un dévelopeur averti et familiarisé avec le parse order, Stash peut accomplir des miracles. A voir aussi, [Mustash](http://devot-ee.com/add-ons/mustash), un add-on payant vous permettant de faire du caching.

### Channel Form

[Chanel Form](http://ellislab.com/expressionengine/user-guide/modules/channel/channel_form/) permet de créer des formulaires pour éditer ou publier des entries sans passer par votre control panel, directement depuis le front-end de votre site.

Channel form est compatible avec de nombreux custom fields parmi les plus populaires et vous permet de créer de véritables petites applications en ligne à l’aide d’ExpressionEngine.

### Add-ons

De nombreux add-ons gratuits ou payants vous permettent d’augmenter les capacités et la flexibilité d’ExpressionEngine.

#### Devot-ee

[Devot-ee](http://devot-ee.com/) répertorie aujourd’hui autour de 2000 add-ons pour ExpressionEngine.

La communauté regorge de développeurs reconnus pour leur travail et offrant un support utilisateur de qualité: [Solspace](http://www.solspace.com/), [EE garage](http://ee-garage.com/) (Leevi Graham & Newism team), [Pixelandtonic](http://pixelandtonic.com/ee) (Brandon Kelly, Brad Bell and Andris Ševčenko), [Go to Low](http://gotolow.com/) (Lodewijk Schutte), [Mark "the" Croxton](http://devot-ee.com/developers/mark-croxton), [Mighty Big Robot](http://mightybigrobot.com/products), [EE-Zoo](http://ee-zoo.com/), [Dev Demon](http://www.devdemon.com/), etc.

#### Développer vos propres add-ons

Si vous souhaitez développer vous même vos propres add-ons, [EllisLab vous propose des instructions détaillées pour ce faire](http://ellislab.com/expressionengine/user-guide/development/).

ExpressionEngine étant développé sur base du framwork MVC open source qu’est [CodeIgniter](http://ellislab.com/codeigniter), les ressources de ce framework sont disponibles et vous permettent de développer des add-ons permettant d'étendre les capacités du système.

## Resources

Les [screencasts de Mijingo consacrés à ExpressionEngine](http://mijingo.com/products/screencasts/learning-expressionengine-2-complete-series/) (Ryan Ierlan) sont une excellente manière de se lancer dans ExpressionEngine de façon didactique.

Si vous préférez quelques tutoriels en ligne pour vous lancer, Mike Boyink de Train-ee vous en propose [quelques-uns en accès gratuit sur son site](http://www.train-ee.com/courseware/free-tutorials). Les ressources payantes valent également la peine.

- ["ExpressionEngine User Guide"](http://ellislab.com/expressionengine/user-guide/): la documentation d'ExpressionEngine par EllisLab.
- ["ExpressionEngine Quick Reference"](http://ellislab.com/expressionengine/user-guide/general/quick_reference.html): bonne cheat sheet par EllisLab.
- [Devot-ee](http://devot-ee.com/): le site de référence en matière d’add-ons pour ExpressionEngine
- [Show-ee](http://www.show-ee.com/): un site sur lequel vous pourrez trouver de nombreux sites réalisés à l’aide d’ExpressionEngine
- [EE-Insider](http://eeinsider.com/): la référence en ce qui concerne les news de la communaut
- [ExpressionEngine stackexchange](http://expressionengine.stackexchange.com/): le site d'aide en ligne de la communauté.
- [Le blog officiel d’EllisLab](http://ellislab.com/blog): de nombreux articles sont consacrés à ExpressionEngine.
- [ExpressionEngine conference](http://www.expressionengineconference.com/): Les conférences annuelles consacrées à ExpressionEngine
- [Vidéos de certains talks à EECI](http://vimeo.com/whoooz) mises à votre disposition par Inspire Conférence et Robert Eerhart
- ["Guide to 4040 Pages with ExpressionEngine"](http://joviawebstudio.com/index_ee.php/blog/guide_to_404_pages_with_expressionengine/): par Ryan Battles
- ["Stash tutorials"](http://www.jamessmith.co.uk/articles/expressionengine-stash-tutorials) par James Smith. Une bonne introduction à Stash et aux apports de cet add-on.
- ["Stash: core principles"](https://speakerdeck.com/croxton/stash-core-principles) et ["Stash: development strategies"](https://speakerdeck.com/croxton/stash-development-strategies) par Mark Croxton: à lire absolument avant de vous lancer dans un build Stash avec ExpressionEngine.