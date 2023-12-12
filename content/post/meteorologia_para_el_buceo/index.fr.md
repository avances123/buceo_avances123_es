---
title: "Météorologie pour la plongée sous-marine"
description: "Quelques idées sur la météo pour les plongeurs"
date: 2022-04-06T00:47:56+01:00
lastmod: 2022-06-06T12:52:12+01:00
draft: false
image: entrada.png.webp
categories:
    - Idées
tags:
    - Mer
    - Documentation
---

# Comment déterminer la météorologie pour la plongée

## Introduction

Chacun d'entre nous, lors de la planification d'une plongée, se préoccupe toujours de l'état de la mer au moment de l'immersion. Notre passe-temps favori se déroule en plein air et **dans** le milieu marin, ce qui fait que nous dépendons énormément de la météorologie pour mener à bien notre plongée.

À mon avis, il est inutile de faire une planification complexe de la plongée et ensuite de négliger une interprétation correcte des conditions météorologiques attendues pour ce jour-là. La météo peut entraîner un report de l'immersion, il est donc important de le savoir avec le plus de certitude possible.

Bien sûr, presque tous ont une façon ou une autre de consulter l'état de la mer pour leurs plongées. En raison de mon intérêt pour le sujet, j'ai toujours posé des questions, et dans presque tous les cas, j'ai constaté que des applications météorologiques pour téléphones portables étaient consultées. Ces applications fournissent des données sur la houle, le vent, etc., sont très pratiques, gratuites et toujours disponibles. Cependant, dans ce billet, je vais me concentrer sur d'autres sources, un peu plus cachées mais non moins utiles, qui nous aideront beaucoup dans cette tâche.

Je vais me concentrer sur des données que je n'ai pas vu être utilisées par qui que ce soit et que je peux apporter à la communauté des plongeurs. Enfin, je parlerai des applications conventionnelles et de certaines améliorations cachées que nous pouvons utiliser pour interpréter et établir une prévision améliorée.

## Facteurs météorologiques à prendre en compte

Pour une bonne planification, nous devrions avoir un ordinateur devant nous et nous concentrer sur plusieurs facteurs météorologiques concernant la plongée. Voici les éléments énumérés. Pour tous ces éléments, nous devons connaître le point géographique de l'immersion et la date, car nous devons consulter les prévisions pour cet endroit et ce moment spécifique.

### Hauteur significative des vagues
À mon avis, c'est la variable déterminante pour la viabilité de l'immersion, et elle nécessite le maximum de précision possible dans les prévisions à cet endroit. Pour cela, sur la péninsule ibérique, j'utilise le modèle météorologique généré par [Ports de l'État](https://www.puertos.es/es-es/oceanografia/AccesoSimplificado). Ce modèle utilise les prévisions de vent de HARMONIE d'AEMET et de HRES-ECMWF pour les horizons suivants après 48 heures. De plus, il fournit des données d'observations de plusieurs bouées installées à proximité des ports, ce qui améliore considérablement le modèle à ces endroits.

Par exemple, si nous voulions savoir quelles vagues nous aurons au site de plongée Dragonera, situé dans le port de Tarragone, nous pourrions consulter le modèle et sa qualité de prédiction à cet endroit.

![Derniers jours de prévision/observation à Tarragone](2.png.webp)

Pour le site de plongée Dragonera, nous avons beaucoup de chance car c'est un endroit pour lequel nous disposons d'observations grâce à une bouée qui enregistre avec une granularité horaire la hauteur des vagues. Il existe plusieurs autres points, toujours des bouées qui aident à la prédiction de la houle _dans les ports_, car les vagues dans le monde portuaire nous intéressent toujours plus que celles du monde de la plongée.

![Bouées avec données mises à jour sur la hauteur des vagues](1.png.webp)

Cela ne signifie pas que nous devons interpoler manuellement la prédiction à l'endroit qui nous intéresse, le modèle lui-même nous fournit une prédiction sur toute la grille de points du modèle. Ainsi, nous pouvons consulter la prédiction pour notre point.

![Points de prédiction des vagues](3.png.webp)

Si nous consultons un point, nous pouvons voir les données sous forme de tableau de toutes les variables du modèle, pas seulement de la hauteur significative, mais aussi du période et de la direction de la vague, de la composante de houle de fond ou de vent de la vague, etc. Il y a également des données sur le vent à cet endroit, ce qui peut toujours être utile pour se faire une idée des vents locaux et de l'état de la mer grâce à une autre voie d'expérience de l'observateur.

![Prévision à un point donné](4.png.webp)

De plus, sur [Copernicus](https://myocean.marine.copernicus.eu/data?view=dataset&dataset=MEDSEA_ANALYSISFORECAST_WAV_006_017), nous disposons de ce modèle WAN sans être amélioré par HARMONIE d'Aemet.

### Température de l'eau

Cette variable nous affecte beaucoup en plongée, mais elle n'est pas réellement prédite car il est assez facile de déduire la température à partir de la date de l'année et des observations antérieures pour cette même date dans le passé.

Sur [Copernicus](https://myocean.marine.copernicus.eu/light), nous pouvons consulter les prévisions de température à notre point d'immersion ainsi qu'un historique du modèle analysé.

![Prévision quotidienne de la température de l'eau](5.png.webp)

Ici, je veux apporter une autre source qui est assez utile pour les voyages de plongée, lorsque nous voulons connaître la température à un endroit de la planète éloigné de notre expérience et de nos latitudes, et lorsque nous voulons savoir quoi emporter comme équipement. Sur [WMO](https://climexp.knmi.nl/monthly_overview_world_weather/index.cgi?var=sst_ncep_w&mon1=jan&year1=2021&anomalie=nee&kort=nee&expert=nee&type=kaartwereld), nous pouvons explorer la température moyenne d'un mois à n'importe quel endroit de la planète. Ce n'est pas précis, mais cela peut nous aider à planifier un voyage en connaissant la date et la destination.

![Informations mensuelles sur la température de l'eau](6.png.webp)

La NASA dispose également d'une autre mission appelée [MUR](https://podaac.jpl.nasa.gov/dataset/MUR-JPL-L4-GLOB-v4.1) qui mesure la température marine à l'échelle mondiale. Elle peut être visualisée avec l'outil de la NASA [worldview](https://soto.podaac.earthdatacloud.nasa.gov/?v=-18.78720059082591,30.727507641081075,21.28282587652165,50.51208320933394).

### Courant

Cette variable nous affecte également en plongée, et quel plongeur n'a jamais rêvé de savoir quel jour il n'y aura pas de courant sur ce site de plongée incroyable ? Cependant, je n'ai pas étudié cette variable autant jusqu'à présent. Je vois qu'il existe une donnée de vitesse de l'eau dans le plan horizontal, mais je ne comprends pas encore quels niveaux verticaux sont utilisés pour mesurer et/ou prédire.

Sur [Copernicus](https://myocean.marine.copernicus.eu/data?view=dataset&dataset=MEDSEA_ANALYSISFORECAST_PHY_006_013), nous pouvons voir les données de courant dans plusieurs ensembles de données, c'est également la variable disponible sur Windy. Je n'ai jamais pu plonger suffisamment de fois pour contraster en tant que plongeur si elle est utile, mais ce serait génial de pouvoir le faire.

![Prévision de courants marins](7.png.webp)

### Pluie et vent
Bien qu'il soit conseillé de consulter également ces variables, je les considère personnellement moins importantes même si elles peuvent entraîner d'autres facteurs tels que la **visibilité** qui nous intéresse, en étudiant les jours passés de pluie et de tempêtes, nous pouvons déduire une mauvaise ou bonne visibilité, par exemple.

Nous pouvons également planifier si nous allons en voilier, ou si le transport de l'équipement nous oblige à marcher sous la pluie ou pour toute autre raison plus extravagante qui pourrait nous affecter. Dans tous les cas, pour ces variables, je renvoie au point suivant sur les applications conventionnelles.

## La voie conventionnelle

Pour consulter la météo à un endroit, nous utiliserons l'application [Windy](https://windy.com). Il y en avait plusieurs autres, mais cette application est de plus en plus populaire auprès de tout le monde car elle regroupe le plus grand nombre de couches, de modèles et de données.

Je recommande, pour une planification sérieuse, d'utiliser un ordinateur plutôt qu'un téléphone portable si possible, car c'est là que nous pouvons utiliser toute l'interface de l'application. Nous pouvons y trouver des informations sur toutes les variables précédemment décrites, bien que nous perdions un peu de précision au niveau du point spécifique, nous gagnons la capacité d'avoir une prévision à n'importe quel endroit de la planète, pas seulement sur la péninsule ibérique.

En plus de consulter la houle ici, nous pouvons également nous renseigner sur "comment sera la journée" en général (température, pluie et vent). Pour ce faire, au lieu d'ouvrir l'application et de consulter la première prévision qu'elle nous fournit, je recommande de faire une vue **multi-modèle** de ces variables, voici comment procéder :

![1. Aller à la prévision du point et cliquer sur le bouton comparer](8.png.webp)

![2. Voir les mêmes données produites par plusieurs modèles](9.png.webp)

Cela nous aidera si nous voyons un consensus dans la prévision ou s'il y a des divergences entre les modèles. C'est toujours la même chose, une consultation de la météo, mais en la regardant à travers 4 ou 5 sources, ce qui peut toujours nous donner une vision plus large du degré d'incertitude que les modèles gèrent pour ce point à ce moment spécifique.
