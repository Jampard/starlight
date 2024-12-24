---
title: Documents écologiques
description: Découvrez comment Starlight peut vous aider à créer des documentations plus écologiques et à réduire votre empreinte carbone.
---

Les estimations de l'impact climatique de l'industrie du web varient entre  et , ce qui équivaut à peu près aux émissions de l'industrie du transport aérien.
Le calcul de l'impact écologique d'un site web repose sur de nombreux facteurs complexes, mais ce guide contient quelques conseils pour réduire l'empreinte écologique de votre site documentaire.

La bonne nouvelle, c'est que le choix de Starlight est un excellent début.
Selon le Website Carbon Calculator, ce site est , produisant 0,01 g de CO₂ par page visitée.

## Poids de la page

Plus une page web transfère de données, plus elle nécessite de ressources énergétiques.
En avril 2023, la page web médiane demandait à l'utilisateur de télécharger plus de 2 000 Ko selon les .

Starlight construit des pages aussi légères que possible.
Par exemple, lors de sa première visite, un utilisateur téléchargera moins de 50 Ko de données compressées, soit seulement 2,5 % de la médiane des archives HTTP.
Avec une bonne stratégie de mise en cache, les navigations suivantes peuvent télécharger jusqu'à 10 Ko.

### Images

Bien que Starlight fournisse une bonne base de référence, les images que vous ajoutez à vos pages de documentation peuvent rapidement augmenter le poids de vos pages.
Starlight utilise le  d'Astro pour optimiser les images locales dans vos fichiers Markdown et MDX.

### Composants d'interface utilisateur

Les composants construits avec des frameworks d'interface utilisateur tels que React ou Vue peuvent facilement ajouter de grandes quantités de JavaScript à une page.
Starlight étant construit sur Astro, les composants de ce type chargent **zéro JavaScript côté client par défaut** grâce à .

### Mise en cache

La mise en cache est utilisée pour contrôler la durée pendant laquelle un navigateur stocke et réutilise les données qu'il a déjà téléchargées.
Une bonne stratégie de mise en cache permet à l'utilisateur d'obtenir un nouveau contenu dès qu'il est modifié, tout en évitant de télécharger inutilement le même contenu à plusieurs reprises lorsqu'il n'a pas changé.

La façon la plus courante de configurer la mise en cache est d'utiliser l'en-tête HTTP .
Lorsque vous utilisez Starlight, vous pouvez définir une longue durée de mise en cache pour tout ce qui se trouve dans le répertoire `/_astro/`.
Ce répertoire contient des fichiers CSS, JavaScript, et d'autres actifs intégrés qui peuvent être mis en cache pour toujours, réduisant ainsi les téléchargements inutiles :

```
Cache-Control: public, max-age=604800, immutable
```

La configuration de la mise en cache dépend de votre hébergeur. Par exemple, Vercel applique cette stratégie de mise en cache pour vous sans configuration nécessaire, tandis que vous pouvez définir des  en ajoutant un fichier `public/_headers` à votre projet :

```
/_astro/*
  Cache-Control: public
  Cache-Control: max-age=604800
  Cache-Control: immutable
```

## Consommation d'énergie

La façon dont une page web est construite peut avoir un impact sur la puissance nécessaire pour fonctionner sur l'appareil d'un utilisateur.
En utilisant un minimum de JavaScript, Starlight réduit la puissance de traitement dont le téléphone, la tablette ou l'ordinateur d'un utilisateur a besoin pour charger et afficher les pages.

Soyez vigilant lorsque vous ajoutez des fonctionnalités telles que des scripts de suivi analytique ou des contenus à forte teneur en JavaScript, comme des vidéos intégrées, car ils peuvent augmenter la consommation d'énergie de la page.
Si vous avez besoin d'analyses, envisagez de choisir une option légère comme , , ou .
Les vidéos intégrées comme celles de YouTube et de Vimeo peuvent être améliorées en attendant de .
Des paquets comme  peuvent aider pour les services communs.

:::tip\[Le saviez-vous ?\]
L'analyse et la compilation de JavaScript est l'une des tâches les plus coûteuses pour les navigateurs.
Par rapport au rendu d'une image JPEG de même taille, \[le traitement de JavaScript peut prendre plus de 30 fois plus de temps\]\[coût-de-js\].
:::

## Hébergement

Le lieu d'hébergement d'une page web peut avoir un impact important sur le degré de respect de l'environnement de votre site de documentation.
Les centres de données et les fermes de serveurs peuvent avoir un impact écologique important, notamment en raison de leur consommation élevée d'électricité et de leur utilisation intensive de l'eau.

Le choix d'un hébergeur utilisant des énergies renouvelables se traduira par une réduction des émissions de carbone pour votre site. Le  est un outil qui peut vous aider à trouver des hébergeurs.

## Comparaisons

Curieux de savoir comment les autres frameworks de documentation se comparent ?
Ces tests avec le  comparent des pages similaires construites avec différents outils.

| Framework | CO₂ par page visitée |
| --------- | -------------------- |
| 0.01g     |                      |
| 0.05g     |                      |
| 0.05g     |                      |
| 0.07g     |                      |
| 0.10g     |                      |
| 0.11g     |                      |
| 0.11g     |                      |
| 0.24g     |                      |
| 0.24g     |                      |
| 0.71g     |                      |

<small>Données collectées le 14 mai 2023. Cliquez sur un lien pour voir les chiffres actualisés.</small>

## Plus de ressources

### Outils

- 
- [GreenFrame](https://greenframe.io/)
- [Ecograder](https://ecograder.com/)
- [WebPageTest Carbon Control](https://www.webpagetest.org/carbon-control/)
- [Ecoping](https://ecoping.earth/)

### Articles et discussions

- [“Building a greener web”](https://youtu.be/EfPoOt7T5lg), conférence de Michelle Barker
- [“Sustainable Web Development Strategies Within An Organization”](https://www.smashingmagazine.com/2022/10/sustainable-web-development-strategies-organization/), article par Michelle Barker
- [“A sustainable web for everyone”](https://2021.stateofthebrowser.com/speakers/tom-greenwood/), conférence de Tom Greenwood
- [“How Web Content Can Affect Power Usage”](https://webkit.org/blog/8970/how-web-content-can-affect-power-usage/), article de Benjamin Poulain et Simon Fraser