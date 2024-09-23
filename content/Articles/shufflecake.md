---
title: "Shufflecake"
description: "This is a demo of adding content to the homepage."
---
<img title="Shufflecake_logo.svg" alt="Logo" src="https://codeberg.org/shufflecake/shufflecake-logo/src/branch/main/shufflecake-logo.svg">

# Introduction

Shufflecake est un outil Linux de chiffrement de volumes puissant, rapide et facile d’utilisation, fonctionnant sur n’importe quel systeme de fichiers.

En complement d’information l’outil est en c et un portage vers du Rust est envisage.

Shufflecake est toujours en cours de developement par *Elia Anzuoni* et *Tommaso “tomgag” Gagliardoni*.

# Les principes du projet

Avant de commencer à utiliser Shufflecake, il est important de comprendre ses principaux concepts pour comprendre ses scénarios d’utilisation.

## Les concepts

### -plausible deniability

Un des concepts est de pouvoir effectuer un deni plausible, mais qu’est-ce qu’un deni plausible ?

Le **déni plausible** ou **possibilité de nier de façon plausible** (« ***plausible deniability*** »
 en anglais) est la possibilité, notamment dans le droit américain, pour
 des individus (généralement des responsables officiels dans le cadre 
d'une hiérarchie formelle ou informelle) de nier connaître l'existence 
d'actions condamnables commises par d'autres dans une organisation 
hiérarchique ou d'en être responsable si des preuves pouvant confirmer 
leur participation sont absentes, et ce même s'ils ont été 
personnellement impliqués ou ont volontairement ignoré ces actions.

Le logiciel en soit ne peut pas être caché lors d’un scan, par contre le nombre de volumes caché quand à lui ne peut être deviné ce qui en fait sa force.

L’idée derrière le logo de l’outil est de visualiser nos volumes en plusieurs couches qui s’ouvrirai avec un mot de passe par couche.

Un mot de passer permet d’accéder jusqu’à son niveau, si on a 15 niveaux et que l’on souhaite aller au 3ème, on utilisera notre 3ème mot de passe qui déverrouillera nos données sur 3 niveaux directement. On peut ainsi graduellement stockée nos informations en fonction de leurs importance. 

### -Ne pas être dépendant de l’ORAM

Qu’est-ce que l’ORAM(Oblivious Random Access Machine) ?

Récemment, la mémoire vive inconsciente (ORAM) est un point qui attire l’attention, car il s'agit d'un outil cryptographique idéal pour masquer les modèles d'accès (access paterns plus d’infos : [https://docs.aws.amazon.com/prescriptive-guidance/latest/dynamodb-data-modeling/step3.html](https://docs.aws.amazon.com/prescriptive-guidance/latest/dynamodb-data-modeling/step3.html))

Une des fonctions primaires d’un cloud est le partage des données, qui est liée à l'évolutivité et à la mutualisation du cloud computing. Ne sachant pas si les données sont bien sécurisée, dans le cloud, on pourrait avoir tendance a vouloir pour des raisons de sécurité et de confidentialité chiffrées nos données. Cependant, les schémas de partage de données existants basés sur ORAM comportent diverses failles :

**une grande complexité de calcul ou une forte dépendance de primitives de cryptographie complexes** (”À la création d’un [système cryptographique](https://fr.wikipedia.org/wiki/Cryptosyst%C3%A8me)
 (ou cryptosystème), le concepteur se fonde sur des briques appelées 
« primitives cryptographiques ». Pour cette raison les primitives 
cryptographiques sont conçues pour effectuer une tâche précise et ce de 
la façon la plus fiable possible.”). 

-Un outil qui a des performances un tout petit peu plus réduite que un système crypte des le départ.

-Un outil qui pourrait être sollicite notamment par lanceurs d’alerte, journalistes d’investigation et militants des droits de l’homme dans les régimes oppressifs. Mais aussi par toute organisation ayant besoin d’un certain niveau de sécurité pour leurs données.

-<maladroit> Cependant, la manière d’accéder aux données n’est parfois pas assez contrôlé (par exemple un mauvais partage de fichiers aux mauvaise personnes)et peut engendrer une fuite d'informations, généralement générés par le comportement des utilisateurs lors du partage de données plutôt que par le contenu des données lui-même. </maladroit>

## Problèmes pour la mise en production:

1.Outil en cours de développement (utilisable plus pour du test)

2.Pas encore de protection contre des multi-snapshot adversaries (TRIM)

3.Du fait de son developement, il peut arriver rarement que il écrive par dessus des données, sur lesquels ils ne devaient pas écrire.

4.Une application bridée a 15 niveau pour l’instant par rapport a son modèle en couche.

5.Ne prévient pas des trojan / keylogger

# Installation et utilisation

apt install git

git clone [https://codeberg.org/shufflecake/shufflecake-c.git](https://codeberg.org/shufflecake/shufflecake-c.git)

Voir pour du logical volume et du volume normal en test

## Pour l’histoire

Il serait potentiel sucesseur a TrueCrypt (qui est plus connue sous le nom de VeraCrypt maintenant), le developpement de TrueCrypt ayant ete interrompue et la derniere version parut nest plus celle disponible aupres du public ce qui est assez etonnant.

# Conclusion:

L’evolution de l’outil est a surveiller de pres etant donne ce que il souhaite apporter dans le domaine.

Lien vers le site officiel:

[https://shufflecake.net/](https://shufflecake.net/)

Lien vers le site d’installation officiel:

[https://codeberg.org/shufflecake/shufflecake-c](https://codeberg.org/shufflecake/shufflecake-c)