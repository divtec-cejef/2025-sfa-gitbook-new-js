# Dates

JavaScript fournit l'objet `Date` pour manipuler les dates et les heures. Voici un aperçu de quelques opérations de base et comment afficher les dates au format français.

### Créer une Date

```javascript
let date = new Date(); // Date actuelle
let specificDate = new Date(2023, 9, 27; // 27 Octobre 2023
```

### Manipuler les Dates

#### Obtenir une date&#x20;

*   <pre class="language-javascript"><code class="lang-javascript"><strong>let jour = date.getDate();
    </strong>let mois = date.getMonth() + 1; // Les mois sont de 0 à 11
    let annee = date.getFullYear();
    </code></pre>



#### **Modifier une date**

```javascript
date.setDate(15);
date.setMonth(11); // Décembre
date.setFullYear(2024);
```

### Formater les Dates

#### Utilisation de `toLocaleDateString()` en JavaScript

`toLocaleDateString()` est une méthode de l'objet `Date` en JavaScript qui permet d'afficher une date dans un format lisible et localisé.

#### Syntaxe de base

```js
let date = new Date();
let dateFr = date.toLocaleDateString('fr-FR');
console.log(dateFr);
```

🔹 Exemple de sortie : `21/05/2025`

***

#### Avec options de format

Tu peux personnaliser l'affichage de la date avec des options.

**🎯 Exemple 1 : Date longue en français**

```js
let date = new Date();
let options = { year: 'numeric', month: 'long', day: 'numeric' };
let dateFr = date.toLocaleDateString('fr-FR', options);
console.log(dateFr);
```

🔸 Sortie : `21 mai 2025`

***

**🎯 Exemple 2 : Avec le jour de la semaine**

```js
let options = { weekday: 'long', year: 'numeric', month: 'long', day: 'numeric' };
let dateFr = new Date().toLocaleDateString('fr-FR', options);
console.log(dateFr);
```

🔸 Sortie : `mercredi 21 mai 2025`

***

**🎯 Exemple 3 : Format abrégé**

```js
let options = { year: '2-digit', month: 'short', day: '2-digit' };
let dateFr = new Date().toLocaleDateString('fr-FR', options);
console.log(dateFr);
```

🔸 Sortie : `21 mai 25`

***

#### Autres locales

Tu peux afficher la date dans d'autres langues simplement en changeant la locale :

```js
let dateUs = new Date().toLocaleDateString('en-US');
console.log(dateUs); // "5/21/2025"
```

```js
let dateDe = new Date().toLocaleDateString('de-DE');
console.log(dateDe); // "21.5.2025"
```

***

#### Résumé

* `toLocaleDateString(locale, options)` permet de personnaliser l'affichage d'une date.
* Très utile pour afficher des dates adaptées à la langue de l’utilisateur.
* Compatible avec tous les navigateurs modernes.
