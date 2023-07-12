# Ember.js Extension Pack

This extension pack adds all extensions to Visual Studio Code you need for developing Ember.js applications.

## Included extensions

* [Ember Language Server](https://marketplace.visualstudio.com/items?itemName=lifeart.vscode-ember-unstable): Adds enhanced editor features like auto completion and go to definition.

* [Glimmer Templates Syntax for VS Code](https://marketplace.visualstudio.com/items?itemName=lifeart.vscode-glimmer-syntax): Ember/Glimmer language extensions offering syntax highlighting for '.hbs, .gts, .gjs' file types, including inline `hbs` and `<template>` tags.

## `.gts` & `.gjs` Support

Since the Typescript Language Server will not be running for these file types, you will need to add the following settings to your `settings.json` file to fill in the gaps. Consider installing [Glint](https://typed-ember.gitbook.io/glint/) to get type checking and hover information.

```jsonc
// add language specific settings
"[glimmer-js]": {
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "editor.foldingStrategy": "indentation"
},
"[glimmer-ts]": {
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "editor.foldingStrategy": "indentation"
},
// enable eslint for glimmer files
{
  "eslint.validate": [
    "glimmer-ts",
    "glimmer-js"
  ],
  "eslint.rules.customizations": [
    { "rule": "*", "severity": "warn" },
  ]
}
```