# Jour 2

### <a href="https://github.com/Joz84/ten-hours-of-html-css" target="_blank">Retour au menu principal</a>

## Lien vers la <a href="https://joz84.github.io/day-b.github.io/" target="_blank">démo</a>

## Les divisions
### Le cadre
Nous souhaitons créer un cadre avec un fond vert autour de chaque section. Pour cela nous avons besoin d'une nouvelle balise : la balise division ```<div></div>```. Par exemple pour la 1ère section :

#### HTML (l.10-16)
```html
 <div>
   <h1>Les Muffins de Grand Mère</h1>
   <h2>Fondants et croustillants</h2>
   <img src="images/muffin.jpg" alt="muffin">
   <br>
   <a href="https://www.marmiton.org/recettes/recette_muffins-tres-simples_166385.aspx">En savoir plus</a>
 </div>
```
Il faut en suite ajouter le CSS associé pour modifier le style du cadre :

#### CSS
```css
div {
 background: lightgreen;
}

```

## Exercice
Encadrer les autres sections avec la balise ```<div>``` pour que celles-ci soient également cadrées comme présenté sur l'image ci dessous :
<img src="images-readme/cadres.png" alt="cadres">

## Les classes
Pour illustrer cette notion nous allons ajouter une section intitulée "Vos productions" sur notre site web. Cette section présente 3 images que l'on a téléchargé et renommé dans le dossier "images". On souhaite modifier le style de ces images pour qu'elles soient plutot rectangulaires.

#### HTML (l.74-79)
```html
  <div>
    <h3>Vos productions</h3>
    <img src="images/production1.jpg">
    <img src="images/production2.jpg">
    <img src="images/production3.jpg">
  </div>
```

#### CSS
```css
img {
  width: 300px;
  height: 200px;
  object-fit: cover;
}
```
Ceci a bien redimentionné les 3 photos mais malheureusement cela a aussi modifié la photo de la 1ère section qui à l'origine été carrée.

Alors comment faire ?

La solution est de "nommer" les images et d'associer le style à ces "noms" plutôt qu'au tag ```<img>```. Ces "noms" sont appellé "class" en HTML. Ainsi les lignes précédentes deviennent :

#### HTML (l.13)
```html
 <img src="images/muffin.jpg" alt="muffin" class="avatar">
```

#### HTML (l.74-79)
```html
  <div>
    <h3>Vos productions</h3>
    <img src="images/production1.jpg" class="production">
    <img src="images/production2.jpg" class="production">
    <img src="images/production3.jpg" class="production">
  </div>
```

Dans le fichier CSS, pour retrouver les images par rapport à leurs classes "avatar" et "production" plutôt que par rapport à leur tag ```<img>```, il suffit d'écrire :

#### CSS
```css
.avatar {
  width: 300px;
  height: 300px;
  object-fit: cover;
}

.production {
  width: 300px;
  height: 200px;
  object-fit: cover;
}
```

Les points "." devant les mots "avatar" et "production" sont là pour indiquer au navigateur qu'il doit chercher des classes et non plus un tag.

## Corrections du code précédent
* On créer une classe ".cadre" que l'on associe à toutes les div comportant un cadre (pour le moment c'est le cas de toutes).
* On créer des classes pour modifier la position du text (.text-center, et .text-left).
* On créer des une classe pour changer la couleur de la police en vert (.color-green).
* On commente toutes les propriétés devenues inutiles.

<i>Remarque :</i> les symboles ```/*...*/``` permet de mettre les lignes en commentaires. Cela veut dire qu'elles ne seront pas vues par le navigateur.  

#### HTML (l.9)
```html
<body class="text-center">
 ...
</body>
```

#### HTML (l.10-12)  
```html
<div class="cadre">
  <h1 class="color-green">Les Muffins de Grand Mère</h1>
  <h2 class="color-green">Fondants et croustillants</h2>
  ...
</div>
```

#### HTML (l.18-19, 27-28, 74-75)
```html
<div class="cadre">
 <h3 class="color-green">...</h3>
 ...
</div>
```

#### HTML (l.32-33, 48-49)
```html
<div class="cadre text-left">
  <h4  class="color-green">Ingredients</h4>
  ...
</div>
```

#### CSS
```css
.text-center {
  text-align: center;
}

.text-left {
  text-align: left;
}

.color-green {
  color: green;
}

.cadre {
background: lightgreen;
}

h1 {
  /*color: green;*/
  font-family: 'Pacifico', cursive;
  font-size: 32px;
}

h2, h3, h4 {
  /*color: green;*/
  font-family: 'Pacifico', cursive;
  font-size: 28px;
}

/*img {
  width: 300px;
  height: 300px;
  object-fit: cover;
}*/

/*h4, ul, ol {
  text-align: left;
}*/

/*div {
background: lightgreen;
}*/
```

## Définir une palette de couleurs plus large

### Les différentes notations des couleurs
Il existe 4 manières différentes de définir une couleur :
* Le nom mais le nombre de couleur est limité, exemple: "pink".
* Le code exadecimal
* Le code rgb (red, green, blue)
* Le code rgba (red, green, blue, transparence). Le dernier paramètre varie entre 0 et 1 et permet de gérer la transparence.

```css
body {
 background: pink;
 background: #FFC0CB;
 background: rgb(255, 192, 203);
 background: rgba(255, 192, 203, 0.2);
}

.color-green {
  color: green;
  color: #008000;
  color: rgb(0, 128, 0);
  color: rgba(0, 128, 0, 0.8);
}
```
<i>Remarque :</i> Pour obtenir différentes teintes de gris, il suffit d'utiliser le code rgb avec 3 fois le même nombre. Par exemple : color: rgb(125, 125, 125);

### Les générateurs de palette de couleurs 
* https://paletton.com/
* https://colorhunt.co/
* https://coolors.co/
* https://www.colourlovers.com/
* https://www.colorzilla.com/
* <a href="https://graphiste.com/blog/choisir-palette-couleurs" target="_blank">10 liens</a>

### Les générateurs de gradients
* https://uigradients.com/
* https://webgradients.com/
* https://cssgradient.io/
* https://www.colorzilla.com/gradient-editor/

### Les générateurs de background SVG
* https://www.svgbackgrounds.com/
* https://www.heropatterns.com/
* <a href="https://bashooka.com/coding/15-svg-css-background-pattern-resources/" target="_blank">15 liens</a>

### Armoniser les images avec les couleurs
* <a href="http://labs.tineye.com/multicolr/" target="_blank">labs.tineye.com</a>
* http://www.colr.org/

### Modification des couleurs dans le fichier CSS

#### CSS
```css
body {
  background: #ee9ca7;  /* fallback for old browsers */
  background: -webkit-linear-gradient(to right, #ffdde1, #ee9ca7);  /* Chrome 10-25, Safari 5.1-6 */
  background: linear-gradient(to right, #ffdde1, #ee9ca7); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
  ...
}
.cadre {
  background: #E2F3DC;
}

.color-green {
  color: #458D2E;
}
```

## De nouvelles propriétés CSS

Les propriétés présentées ici permettent de modifier les marges interieures et exterieures les arrondis des angles les contours et les ombres d'une box. Nous prendrons comme exemple la box ".cadre".

### Définitions des propriétés
* border: les contours
* margin: marges extérieures
* padding: marges intérieurs
* border-radius: l'arrondi des angles
* box-shaddow: l'ombre portée

<img src="images-readme/boxmodel.png" alt="boxmodel">

### Modification de ces propriétés dans le fichier CSS

#### CSS
```css
.cadre {
  background: #E2F3DC;
  border: 3px solid #C1E6B6;
  margin: 20px 100px;
  padding: 30px 70px;
  border-radius: 5px;
  box-shadow: 5px 5px 10px grey;
}

.avatar {
  width: 300px;
  height: 300px;
  object-fit: cover;
  border-radius: 50%;
  box-shadow: 5px 5px 10px grey;
}

.production {
  width: 300px;
  height: 200px;
  object-fit: cover;
  border-radius: 3px;
  box-shadow: 2px 2px 10px grey;
  margin: 10px;
}
```

### Mise en forme du bouton

#### HTML (l.15)
```html
  <a href="https://www.marmiton.org/recettes/recette_muffins-tres-simples_166385.aspx" target="_blank" class="btn-pink">En savoir plus</a>

```
#### CSS

```css
.btn-pink {
  display: inline-block;
  color: white;
  background: #C86472;
  margin: 20px;
  padding: 20px;
  border-radius: 5px;
  font-weight: bold;
}

.btn-pink:hover {
  color: white;
  opacity: 0.8;
}
```
