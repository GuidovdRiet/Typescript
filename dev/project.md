## Een startproject clonen

- Je kan in week 0 van PRG 4 een leeg startproject vinden met alle instellingen voor VS Code.

## Zelf een startproject maken 

- Maak een DEV en een DOCS folder.
- In DOCS plaats je je HTML + CSS + JS bestanden.
- In DEV plaats je je .ts files
- Maak een `tsconfig.json` file met onderstaande settings.
- Maak een `tasks.json` volgens onderstaande instructies.

## tsconfig.json

Dit bestand bepaalt hoe je typescript wordt gecompileerd naar Javascript, en hoe streng je code op fouten wordt gecontroleerd. 

```
{
    "compilerOptions": {
        "sourceMap":  true,
        "removeComments": true,
        "noImplicitAny": true,
        "noImplicitReturns": true,
        "noUnusedLocals": true,
        "target":"es5",
        "out": "docs/js/main.js"
    },
    "exclude": [
        "node_modules",
        "docs"
    ]
}
```

## Build task maken in VS Code

- Open het task menu met `CMD+P` (mac) of `CTRL+P` (windows)
- Typ `> configure` en kies voor `configure task runner`
- Kies `Typescript with Watch Mode`.

Je kan ook onderstaande `tasks.json` file copy>pasten en in de map `.vscode` plaatsen:

```
{
    "version": "0.1.0",
    "command": "tsc",
    "isShellCommand": true,
    "args": ["-w", "-p", "."],
    "showOutput": "always",
    "isBackground": true,
    "problemMatcher": "$tsc-watch"
}
```

## Links

- [Opties voor tsconfig.json](https://www.typescriptlang.org/docs/handbook/compiler-options.html)
- [Tasks in VS Code](https://code.visualstudio.com/docs/editor/tasks)