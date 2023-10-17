# Atelier React

## commencons

que savez vous de react :
c'est une librairie créé par facebook, permet de créer des composants reutilisables, et facilite la communications entre les differents compasants
1- C'est un wireFrame pour constuire une app.
2- Il structure l'arborescence de l'application, pour une meilleure gestion de differentes fonctionnalités.

## plus de concepts

### qu'est ce que JSX :

C'est un language de progrmmation qui permet d'utiliser le XML dans JS, aussi connu sous le nom de JS XML

```jsx
return (
  <div className="cell">
    <h4>Group Name</h4>
    <input type="color" value={cellColor} onChange={(e) => changeColor(e)} />
    <hr />
    {listPrisoners.map((prisoner) => (
      <h6 key={prisoner.id} style={{ backgroundColor: cellColor }}>
        {prisoner.name}{" "}
      </h6>
    ))}
  </div>
);
```

### Quels sont les composants :

Un composant est un élément de l'application qui represente un bout de code (visuel et logique) réutilisable, il permet d'isoler un element, et les interactions eventuelles qui y sont liées. en bonne pratique, un composant est presenté par un fichier, et il est recommandé d'utiliser l'extension .jsx
Il y a deux facons de créer un composants :

- par fonction

```jsx
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}
```

- par class

```jsx
class Welcome extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}
```

### quels sont les props

Les props snt les propriétés que l'on peut passer à un composant React, à la phase de l'initialisation du composant.
les props sont immutables, donc on ne peut pas changer leurs valuers dans le composant.

### qu'est ce que le state?

Comme le props sont immutables, les states stoquent les valeurs changeables, qui actualise l'affichage du composants

## Vite

Vite a été créer par Evan YOU.
Outil de developpement rapide pour la création d'application web utilisant JavaScript.
Son point fort réside dans sa haute vitesse de compilation et d'execution grace au modules utilisées.
Il généralement utilisé en combinaison avec React.
Pour créer un projet en utilisant vite:

- Dans un terminal :

```bash
npm create vite@latest react-atelier
```

ensuite on suit les instructions afins de choisir le framework et le language à utiliser
Une fois terminer, on utilise les trois commandes

```bash

  cd react-atelier
  npm install
  npm run dev
```

### Fichiers du projet

- Dossier public : contient les fichiers accessible de l'exterieur de l'application, comme les images et les logos
- src : contient :

  1. Dossier assets: contenant les images et les medias durant la phase du developpement, ces contenus seront transmits dans le fichier public après le build.
  2. App.css : le fichier style importé au composant App.jsx, il peut être importé à plusieurs composants simultanément
  3. App.jsx : le composant parent, le point d'entrée principale de l'application, qui contient tout les éléments enfants. C'est la structure principale de l'application React.
  4. index.css : le fichier style de la page index.html
  5. main.jsx : utilisé pour initialiser l'application et definir les points d'entrées et inclure le composant racine. c'est le fichier qu on execute pour demarrer l'application, on peut y inclure des configuration et des dependences importantes comme Rect et ReactDOM

  ```jsx
  import React from "react";
  import ReactDOM from "react-dom/client";
  ```

  dans le composant main, on cherche l'element HTML qui va heberger notre visuael de l'application, dans ce cas on cherche la "div" qui a un identifiant "root", et on place notre lement parent `<App />`

  ```jsx
  ReactDOM.createRoot(document.getElementById("root")).render(
    <React.StrictMode>
      <App />
    </React.StrictMode>
  );
  ```

  6.  .eslintrc.cjs : verificateur de code: le fichier qui contient les règles de verification du code.
  7.  .gitignore: le fichier annuaire qui regroupe l'ensemble de fichiers et dossiers à ignorer pendant le transfert du ripositoire dans un hebergeur en ligne comme github.
  8.  index.html, la page root, qui est heberge notre l'application, c'est la page chargé par le navigateur web, et qui sers comme point de départ de l'appli dans le DOM. Notez que la page index.html, charge le fichier main.jsx au démarage.
  9.  package-lock.json : liste les dependances et les dependance de dependances.
  10. package.json : un fichier qui liste les dependances de notre appli , ainsi qu'une partie configurable "script" qui sera chargée d'executer des instructions suivant la phase de developpement

  ```json
  "scripts": {
    "dev": "vite",
    "build": "vite build",
    "lint": "eslint . --ext js,jsx --report-unused-disable-directives --max-warnings 0",
    "preview": "vite preview"
  }
  ```

  par exemple , duran la phase de developpement: on peut executer la commande
  `npm run dev` 11. README.md : c'est le fichier contenant ce texte, qui explique le projet, ces axes de developpement, la license d'utilisation, il cite également les bugs et les potentiels mises à jours. 12. vite.config.js : fichier de configuration de l'outil "vite"

  ```js
  import { defineConfig } from "vite";
  import react from "@vitejs/plugin-react";
  // https://vitejs.dev/config/
  export default defineConfig({
    plugins: [react()],
  });
  ```

  par exemple ce fichier configure vite pour utiliser react, ce fichier peut être configurer différemment, pour utiliser un autre framework par exemple ou un autre language du meme framework.
