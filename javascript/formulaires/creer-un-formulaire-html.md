---
description: >-
  Dans ce cours, tu apprendras à créer un formulaire HTML structuré, accessible
  et complet.
---

# Créer un formulaire HTML

### 1. Structure générale <a href="#id-1-structure-generale" id="id-1-structure-generale"></a>

Un formulaire HTML se définit à l’aide de la balise `<form>`. Il contient des champs de saisie organisés en liste, pour améliorer la lisibilité du code :

```html
<form action="https://kode.ch/getpost/" method="POST">
    <ul>
        <li>
            <!-- Champs de formulaire ici -->
        </li>>
    </ul>
</form>
```

* **action** : URL de destination des données.
* **method** : `GET` ou `POST` selon le type d’envoi.
  * `GET`  pour un formulaire qui var **récupéré, rechercher des données**, comme celui de Google.
  * `POST` pour un formulaire qui va **envoyer des données**, par exemple le formulaire pour créer un compte Amazon.

### 2. Champ texte simple <a href="#id-2-champ-texte-simple" id="id-2-champ-texte-simple"></a>

Chaque champ est généralement composé d’un `<label>` lié à un `<input>` via l’attribut `for` (dans le label) et `id` (dans l’input).

```html
<label for="hauteur">Hauteur</label>
<input type="text" id="hauteur" name="hauteur" value="100" autofocus>
```

* `name` est utilisé pour transmettre la valeur au serveur.
* `value` est la valeur par défaut.
* `autofocus` place le curseur automatiquement sur ce champ au chargement, à placer sur un seul champ par page.

#### Champs dérivés du type texte

Les champs dérivés du type texte incluent des spécificités pour différentes entrées :

*   **Mot de passe (`<input type="password">`)** : Masque les caractères saisis pour la discrétion.

    ```html
    <label for="mdp">Mot de passe</label>
    <input type="password" id="mdp" name="mdp">
    ```
*   **Email (`<input type="email">`)** : Vérifie que l'entrée respecte le format d'une adresse email.

    ```html
    <label for="email">Email</label>
    <input type="email" id="email" name="email">
    ```
*   **URL (`<input type="url">`)** : S'assure que l'entrée est une URL valide.

    ```html
    <label for="site">Site web</label>
    <input type="url" id="site" name="site">
    ```

{% embed url="https://www.w3schools.com/html/html_form_input_types.asp" %}
Tous les types de input
{% endembed %}

### 3. Menu déroulant (`<select>`) <a href="#id-3-menu-deroulant-select" id="id-3-menu-deroulant-select"></a>

Pour proposer à l'utilisateur de faire un choix parmis une grande liste de prpositions, plus de six.

Si le nombre de choix est inférieurs à six, on préférera un groupe de [boutons radios](creer-un-formulaire-html.md#id-4-boutons-radio-input-typeradio).

```html
<label for="fond">Couleur de fond</label>
<select name="fond" id="fond">
  <option value="blue">Bleu</option>
  <option selected value="yellow">Jaune</option>
  <option value="red">Rouge</option>
  <option value="green">Vert</option>
</select>
```

* L’attribut `selected` indique l’option sélectionnée par défaut.

### 4. Boutons radio (`<input type="radio">`) <a href="#id-4-boutons-radio-input-typeradio" id="id-4-boutons-radio-input-typeradio"></a>

Utilisé quand l’utilisateur doit faire **un seul choix** parmi une liste de choix restreint, maximum six.

```html
<fieldset>
  <legend>Couleur du texte</legend>
  <input type="radio" name="color" id="noir" value="black" checked>
  <label for="noir">Noire</label>

  <input type="radio" name="color" id="blanc" value="white">
  <label for="blanc">Blanche</label>

  <input type="radio" name="color" id="rose" value="pink">
  <label for="rose">Rose</label>
</fieldset>
```

* Tous les boutons partagent le même `name`, ce qui force un choix unique.
* Le champ coché par défaut a l’attribut `checked`.

### 5. Cases à cocher (`<input type="checkbox">`) <a href="#id-5-cases-a-cocher-input-typecheckbox" id="id-5-cases-a-cocher-input-typecheckbox"></a>

Pour permettre **plusieurs choix indépendants** :

```html
<fieldset>
  <legend>Style du texte</legend>
  <input type="checkbox" name="gras" id="gras">
  <label for="gras">Gras</label>

  <input type="checkbox" name="souligne" id="souligne">
  <label for="souligne">Souligné</label>
</fieldset>
```

* Chaque case a un `name` unique si on souhaite identifier indépendamment chaque choix.

### 6. Zone de texte (`<textarea>`) <a href="#id-6-zone-de-texte-textarea" id="id-6-zone-de-texte-textarea"></a>

Pour saisir plusieurs lignes de texte :

```html
<label for="txt">Texte</label>
<textarea name="txt" id="txt" rows="2" cols="20">Votre texte</textarea>
```

### 7. Boutons de formulaire <a href="#id-7-boutons-de-formulaire" id="id-7-boutons-de-formulaire"></a>

Deux types de boutons sont couramment utilisés :

```html
<button type="reset">Réinitialiser</button>
<button type="submit">Modifier le rectangle</button>
```

* `type="reset"` : remet le formulaire à son état initial.
* `type="submit"` : envoie les données du formulaire.

### 8. Champ caché

Les champs cachés permettent de stocker des données qui ne sont pas visibles ou modifiables par l'utilisateur, mais qui doivent être envoyées au serveur lors de la soumission du formulaire.

```html
<input type="hidden" id="session-id" name="session-id" value="123456">
```

* Utilisé pour transmettre des informations telles que les IDs de session ou d'autres données contextuelles.

### 9. Bonnes pratiques <a href="#id-8-bonnes-pratiques" id="id-8-bonnes-pratiques"></a>

* Utilise toujours un `<label>` pour chaque champ.
* Regroupe les options (radio ou checkbox) dans un `<fieldset>` avec `<legend>`.
* Organise les champs dans des `<li>` pour plus de lisibilité.
* Préfère des noms de champs explicites (`name`, `id`).

