# Flutter GH Pages

Automates the build and deployment of your Flutter web app on Github gh pages

# Action

To use this action, create an action like the following on your workflows folder

```yml
name: Gh-Pages

on:
  push:
    branches: [ master ]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v2
      - uses: subosito/flutter-action@v1
      - uses: erickzanardo/flutter-gh-pages@v3
```
To build a project in a folder other that the root, use the `workingDir` property

```yml
      ...
      - uses: erickzanardo/flutter-gh-pages@v3
        with:
          workingDir: example
```

By default, the action will use the auto setting for web renderers, to change that you can use the webRenderer property.

More on web renderers here: https://flutter.dev/docs/development/tools/web-renderers

```yml
      ...
      - uses: erickzanardo/flutter-gh-pages@v3
        with:
          webRenderer: canvaskit
```
