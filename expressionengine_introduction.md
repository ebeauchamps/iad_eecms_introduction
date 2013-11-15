# ExpressionEngine: Introduction

## ExpressionEngine

ExpressionEngine est un CMS flexible développé par EllisLab et basé sur PHP et MySQL. ExpressionEngine est développé sur base d’un framework PHP open-source: CodeIgniter Ses fonctionnalités peuvent donc facilement être étendues à l’aide d’add-ons rédigés dans ce langage.

A mes yeux, les grands atouts d’ExpressionEngine sont:

- Le fait qu’il s’agit d’un produit payant derrière lequel se trouve une compagnie: ElliLab. Cela vous donne un interlocuteur unique en cas de problème et permet un développement continu du produit.
- Sa nature modulaire qui lui donne une grande flexibilité tout en restant simple d’utilisation. Ce CMS s’adapte à la nature et à la structure de vos données et de votre méthode de travail, et pas l’inverse.
- Une documentation complète et mise à jour, ainsi qu’une communauté de développeurs et d’utilisateurs des plus serviable et amicale.

Bref, si vous êtes développeur front-end, ExpressionEngine est un excellent CMS vous permettant de réaliser des sites complexes, même sans maîtrise de PHP ou de MySQL. Si êtes développeur, back-end, vous trouverez en ExpressionEngine et en CodeIgniter un framework puissant et extensible.

Si ExpressionEngine n’est pas encore très connu en Europe et en Belgique, il a cependant un pedigré intéressant et des références impressionnantes.

## Definir et structurer vos Contenus

### Channels

Les channels occupent une place centrale dans le mode de fonctionnement d’ExpressionEngine et sont au coeur de sa flexibilité. La plus grande partie des contenus du site vont être défini et structurés sur base des channels.

Si vous avez besoin d’une métaphore, pensez à vos channels comme à des tables dans une bases de données. Les channels sont les outils pricipaux à l’aide desquels vous allez organiser et structurer les informations de votre futur site.

**Exemples:** channel "news", channel "événements", channel "produits"

D’autre éléments vont venir se greffer sur ces channels pour définir plus précisément les éléments de contenu (entries) qui y sont stockés.

### Field Groups, Custom Fields et Field Types

ExpressionEngine vous permet de définir des champs et des groupes de champs. Chacun de ces groupes de champs peut être associé à un ou plusieurs channels et défini la structure des éléments stockés par ceux-ci.

Ces groupes de champs peuvent contenir des champs de différents types (fichiers, texte simples, zones de textes, liste de choix, cases à cocher, relations, grilles, etc.)

Si les channels sont des tables dans une base de données, les champs sont les colonnes définissant le contenu de chacune des tables

Exemple: Pour un channel "évenements" on aura par exemple les champs suivants:

- Titre
- Date de début
- Date de Fin
- Résumé
- Description étendue
- URL du site de l’événement

ExpressionEngine permet nativement d’utiliser un nombre limité de type de champs. De nombreux add-ons gratuits et payants vous permettent de disposer d’un éventail plus large.

Moyennant une connaissance de base de PHP et à l’aide de la documentation fournie par EllisLab, vous pouvez facilement créer de nouveaux types de champs adaptés aux besoins du projet.

### Status

Chaque entry dans un channel possède une structure bien précise, définie par les champs associés au channel. Chaque entry possède également un statut. Les statuts sont généralement utilisés pour déterminer le statut de publication d’un item donné (publié, non- publié, en révision, brouillon, etc.).

Par défaut, les channels sont associés à un groupe de statuts de base définissant seulement deux états: publié et non-publié. Vous pouvez soit ajouter des statuts à ce groupe, soit créer d’‘autres groupes de statuts que vous pourrez ensuite lier à un ou plusieurs channels.

### Catégories

Vous pouvez également définir des groupes de catégories qui peuvent ensuite être liés à un ou plusieurs channels. Au sein de ces groupes, les catégories peuvent être hiérarchisées ou pas.

### Stocker vos fichiers

ExpressionEngine vous offre également une solution pour stocker vos fichiers (PDF, images, fichiers videos, sons, etc.) ailleurs que dans vos channels et vos custom fields.

### Upload Preferences

Vous pouvez définir autant de dossiers (upload preferences) que nécessaire sur votre serveur pour stocker vos fichiers. A nouveau, ExpressionEngine ne vous oblige pas à travailler d’une façon particulière. Vous pouvez choisir de classer vos fichiers par type, par channel ou de toute autre façon qui vous convienne.

Ces upload preferences vous permettent de classer vos fichiers à l’aide de dossiers. Elles vous permettent aussi d’introduire des restrictions quant aux caractéristiques des fichiers qui peuvent être uploadés dans ces dossiers: taille des images, poids des fichiers, type de fichiers, etc.

Les channels et les custom field font ensuite référence aux fichiers stockés dans ces différents dossiers. Vous pouvez également travailler directement avec vos fichiers, sans passer par des channels ou des custom fields, en utilisant le file module et les tags qui s’y rapportent.

### File manager

Le File Manager vous permet, comme son nom l’indique, de gérer vos différents fichiers et éventuellement de réaliser des opérations simples telles que le redimensionnement ou la rotation d’images.

## Templates: afficher vos données

### Template groups et Templates

ExpressionEngine vous permet de définir des groupes de templates et des templates au sein de ceux-ci. Ces templates sont hybrides en ceci qu’ils contiennent à la fois du code HTML / CSS / Javascrit / XML / etc. et des tags propres au langage de templating d’ExpressionEngine.

Ces templates vont définir la manière dont sont affichées les données que vous avez structurées précédemment.

### Structure des URLS

La structure des URL dans un site ExpressionEngine est par défaut définie par la forme suivante:

```
template_group/template/url_title
```

Les tags ci-après sont les plus utilisés pour créer des liens entre des pages dynamiques:

- `{path="template_group/template"}` créera un lien vers un template précis dans un template group
- `{url_title_path="template_group/template"}` créera un lien vers un template précis dans un template group en ajoutant l’url title de l’entry à la fin de l’URL. Utilisé pour les pages de détail affichant une entry

Attention, les templates d’index dans les divers template groups n’apparaissent pas dans les structure d’URL.

Expressionenigne fait passer toutes les requêtes http par un fichier index.php qui apparait donc dans toutes les URL. Le module Mod Rewrite et des fichiers .htaccess peuvent êtres utilisés pour retirer la mention de ce fichier des URL. Ma méthode préférée est la «exclude method» détaillée dans le wiki et à laquelle un article est consacré sur devot-ee.

### Tags

ExpressionEngine possède de nombreux tags et paramètres vous permettant d’afficher vos données et de réaliser certains tests et traitement de celles-ci avant affichage. Nous nous contenterons ici d’examiner les plus utilisés: les entry loops et les structures de contrôle ou conditionnels.

#### Channel Entries loops

La tag pair channel entries est votre outil de travail principal lorsque vous codez des templates. Cette tag pair vous permet d’afficher les données stockées dans vos channels. De nombreux paramètres sont disponibles et vous permettent de cibler vos requêtes.

```
{exp:channel:entries channel="channel_short_name" disable="custom_fields|categories|category_fields|member_data|pagination|trackbacks" orderby="date" sort="desc" limit="10" dynamic="no"}
	{title}
{/exp:channel:entries}
```

- **Channel**: vous permet de sélectionner le channel que vous visez. Il est possible d’aller chercher des entries dans plusieurs channels channel=”news|events” ou encore de travailler par exclusion plutôt que par inclusion channel=”not news”.
- **Disable**: est un paramètre d’optimisation. Si vous n’avez pas besoin de quelque chose, spécifiez-le ici. Ce paramètre évite au système d’allouer des ressources à des tâches non nécessaires.
- **Orderby** et Sort: permettent de classer les entries selon certains critères: date de publication, titre, custom field, ... et de les afficher en ordre croissant ou décroissant. Ces paramètres peuvent être chaînés: orderby=”title|date” sort=”asc|asc”
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

Il existe des add-ons gratuits étendant les possibilités des structures conditionnelles de base et modifie leur ordre de préséance dans l’exécution des operations par ExpressionEngine. Les plus connus et les plus utilisés sont dans doute Switchee et IfElse développés par Mark Croxton.

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

Contiennent de petites informations comme des introductions ou des petits contenus isolés que vous souhaitez tout de même pouvoir mettre à jour facilement. Ne peuvent pas contenir de tags ExpressionEngine

`{gv_news_page_intro}`

#### Snippets

Eléments dynamiques pouvant faire appel au contenu des channels et pouvant donc contenir des tags ExpressionEngine

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

### Member groups et Members

ExpressionEngine vous permet de définir des groupes d’utilisateurs et d’associer des membres à ces groupes. Ces divers groupes d’utilisateurs vont vous permettre de contrôler, avec une grande granularité, les privilèges que vous accordez aux membres de ces groupes.

Vous pouvez, par exemple, moduler les accès à l’interface d’administration du site ou à certaines zones de ce dernier, donner ou non accès à certaines fonctionnalités ou à certains add-ons, etc.

Même si le système de membership d’ExpressionEngine est assez complet, il ne suit pas la même logique que les channels et les templates. Par conséquent, si votre site repose sur des fonctionnalités nécessitant des comptes utilisateurs et des options de gestion de ces derniers, quelques add-ons vous simplifieront la vie.

- User (Solspace) vous permettra de gérer plus facilement vos membres et les templates y étant liés. A l’aide de cet add-on, mettre en place et intégrer un système de membership et de gestion des profils utilisateurs au sein de votre site est un jeu d’enfant.
- Si vous avez besoin pour vos fonctionnalités de membership de toute la flexibilité que vous offent les channels et les custom fields, Zoo Visitors (EE-Zoo) et Profile:Edit (Mighty Big Robot).

## Pour aller plus loin

Ces quelques pages ne contiennent qu’une introduction à ExpressionEngine. Ce système offre bien d’autres possibilités que vous serez amenés à utiliser si vous aller plus loin qu’une simple introduction.

### Etapes de configuration

Lorsque vous mettez en place un site ExpressionEngine, il convient de faire les choses dans un certain ordre pour être efficace. Voici la procédure standard

1. **Installer vos add-ons**: Certains add-ons interagissent avec les members, les fichiers et les channels. Il est donc préférable de les installer dès le début.

2. **Mettre en place vos Member Groups**: Vous devrez certainement utiliser ces member groups dans les étapes suivantes. Typiquement, vous aurez un groupe pour les super-admins (le client en est généralement exclu) et un groupe pour les administrateurs de contenu. Certains autres groupes peuvent également être créés dans le cadre de certains projets. Vous devrez revenir aux Member Groups par la suite, mais mettez déjà en place ce dont vous avez besoin.

3. **Configurer vos Upload Destinations**: les Member Groups sont déjà en place pour spécifier vos permissions.

4. **Configurer vos Category Groups et vos catégories initiales**: vous pourrez spécifier les permissions des member groups relatives aux catégories. Les File Upload Destinations pourront être utilisées pour les images des catégories.

5. **Configurer les Status Groups et les Status**: Les Member Groups sont déjà en place pour vous permettre d'assigner les permissions.

6. **Configurer les Custom Fields pour chaque Channel**: les File Upload Destinations et les add-ons de type Fieldtypes sont déjà en place. N'oubliez pas d'écrire vos instructions au fur et à mesure. 

7. **Configurer les Channels**: Vos Category Groups, Status Groups et Custom Fields sont déjà en place.

8. **Terminer la configuration des member groups**: vous pouvez maintenant revenir aux Member Groups et leur asiigner les permissions pour les Channels et Modules, ainsi que faire les dernier réglages.

### Fichiers de configuration dynamiques

Lorsqu’on développe un site de manière professionnelle aujourd’hui, il est courant de devoir gérer différents environnements server pour un même site: développement, staging, production.

ExpressionEngine permet aux utilisateurs confirmés de configurer une installation sans forcément utiliser le control panel, en passant uniquement par un fichier de configuration. Cette approche offre un gain de temps notable et augmente également la flexibilité de votre installation en terme d’environnements serveurs.

Quelques astuces PHP permettent de rendre ce fichier de configuration dynamique et de passer rapidement d’un serveur à un autre sans devoir configurer l’ensemble des paramètres du site à chaque fois que l’on change de serveur. Voici quelques articles intéressants détaillant cette procédure, ainsi que la liste des paramètres utilisables dans le cadre de ces fichiers de configuration.

### Channel Form

Chanel Form permet de créer des formulaires pour éditer ou publier des entries sans passer par votre control panel, directement depuis le front-end du site.

SafeCracker est compatible avec de nombreux custom fields parmi les plus populaires et vous permet de créer de véritables applications en ligne à l’aide d’ExpressionEngine.

### Add-ons

De nombreux add-ons gratuits ou payants vous permettent d’augmenter les capacités et la flexibilité d’ExpressionEngine. Devot-ee répertorie aujourd’hui 859 add-ons pour ExpressionEngine.

La communcauté comporte pas mal de développeurs reconnus pour leur travail et offrant un support utilisateur de qualité: Solspace, EE garage (Leevi Graham), Pixelandtonic (Brandon Kelly & team), Go to Low (Lodewijk Schutte), Mark Croxton, Mighty Big Robot, EE-Zoo, etc.

Si vous ne trouvez pas votre bonheur ou si vous souhaitez développer vous même vos propres add-ons, EllisLab vous propose des instructions détaillés pour ce faire. ExpressionEngine étant développé sur base du framwork MVC open source qu’est CodeIgniter, les ressources de ce framework sont disponibles et vous permettent de développer des add-ons relativement complexes en en temps record.

## Resources

Les screencasts de Mijingo par Ryan Ierlan sont une excellente manière de se lancer dans ExpressionEngine de façon didactique

Si vous préférez quelques tutoriels en ligne pour vous lancer, Mike Boyink de Train-ee vous en propose deux en accès gratuit sur son site train-ee. Les autres ressources (payantes) valent également la peine.

Getting Started with ExpressionEngine 2 par Ellislab

- Devot-ee: le site de référence en matière d’add-ons pour ExpressionEngine
- Show-ee: un site sur lequel vous pourrez admirer de nombreux sites réalisés à l’aide d’ExpressionEngine
- EE-Insider: la source de référence en ce qui concerne les news de la communauté
- Le blog officiel d’EllisLab consacré à ExpressionEngine.
- Les conférences annuelles consacrées à ExpressionEngine
- Certaines videos des précédentes éditions de EECI mises à votre disposition par Whoooz! et Robert Eerhart