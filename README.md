[![Build Status](https://travis-ci.org/RobertHeim/phpbb-ext-topictags.svg?branch=master)](https://travis-ci.org/RobertHeim/phpbb-ext-topictags)
[![Scrutinizer Code Quality](https://scrutinizer-ci.com/g/RobertHeim/phpbb-ext-topictags/badges/quality-score.png?b=master)](https://scrutinizer-ci.com/g/RobertHeim/phpbb-ext-topictags/?branch=master)

phpbb-ext-topictags
===================

phpBB 3.3 extension, ajoute la capacité d'étiqueter les sujets avec des mots clés (Tag).

## Caractéristiques

### Usages

* Ajouter des balises lors de la publication d'un nouveau sujet
* Suggestions d'étiquettes basées sur les étiquettes existantes
* Etiquettes d'édition lors de l'édition du premier poste de sujet
* Optimisation SEO: les étiquettes sont ajoutées aux mots-clés méta-contenu dans viewtopic
* Les étiquettes sont affichées dans viewforum (peut être désactivé dans ACP)
* Permettre le marquage des sujets par forum
* Totalement Responsive layout
* Support intégral de l'UTF-8

### Recherche
* Sujets de recherche par étiquette(s) au clic sur un Tag
* /tag/{tags}/{mode}/{casesensitive} affiches montre des sujets marqués avec tous (mode=AND, default) ou n'importe lequel (mode=OR) des balises données, où les balises sont des étiquettes séparées par la virgule et que la caseste peut être fidèle à la recherche de cas-sensible ou faux (défaut), par exemple:
  * */tag/tag1,tag2/OR* lists topics that are tagged with tag1 OR tag2 OR tAG2
  * */tag/tag1,tag2/AND* lists topics that are tagged with \[tag1 AND (tag2 OR tAG2)\]
  * */tag/tag1,tag2* lists topics that are tagged with \[tag1 AND (tag2 OR tAG2)\] (mode=default=AND, casesensitive=default=false)
  * */tag/tag1,tAG2/AND/true* lists topics that are tagged with (tag1 AND tAG2)

### Étiquette-Cloud
* /tags shows a tag cloud
* acp option for tag cloud to be displayed on board-index or not
* acp option to limit count of tags shown in tag cloud on the index page
* dynamic tag-size in tag cloud depending on its usage count
* acp option to en/disable display of usage count of tags in tag cloud

### Configuration avancée
* configure a regex to decide which tags are valid and which are not
* maintenance functions in ACP -> Extensions -> RH Topic Tags
* Whitelist
* Blacklist
* User and Mod+Admin permission for who can add/edit RH topic tags
* spaces in tags are converted to "-" by default (you can disable it in ACP)
* Manage existing tags in ACP
  * Delete tag
  * Rename tag
  * Merge tags (rename one tag to the same name as another tag and they will automatically be merged )

## Installation

### 1. clone
Clone (or download an move) the repository into the folder phpBB3/ext/robertheim/topictags:

```
cd phpBB3
git clone https://github.com/RobertHeim/phpbb-ext-topictags.git ext/robertheim/topictags/
```

### 2. activate
Go to ACP -> tab Customise -> Manage extensions -> enable RH Topic Tags
Go to ACP -> Forums -> edit/create any forum -> set *Enable RH Topic Tags* to *Yes*

### 3. configure

Goto ACP -> Extensions -> RH Topic Tags

## Update

Go to ACP -> tab Customise -> Manage extensions -> disable RH Topic Tags

```
cd phpBB3/ext/robertheim/topictags
git pull
```

Go to ACP -> tab Customise -> Manage extensions -> enable RH Topic Tags

## Support

https://www.phpbb.com/community/viewtopic.php?f=456&t=2263616
