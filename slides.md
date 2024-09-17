---
theme : "night"
transition: "slide"
highlightTheme: "monokai"
slideNumber: false
title: "VSCode Reveal intro"
---

### Outils pour se Simplifier le Développement

---

# $ whoami

- Présentateur récidiviste
- Dev & Ops
- Paresseux
- <3 Outils

---

# ToC

- IDE
- EditorConfig
- Type Systems
- Input Validation
- Tests
- CI/CD
- Semantic-Release
    - Conventional Commits



---

# VSCode
|`.vscode/`||
|---|---|
|`extensions.json`|Recommandations d'extensions|
|`launch.json`|Débugging|
|`settings.json`|Configuration IDE/Extensions|

---

# EditorConfig

`.editorconfig`
```
# EditorConfig is awesome: https://editorconfig.org

# top-most EditorConfig file
root = true

# Unix-style newlines with a newline ending every file
[*]
end_of_line = lf
indent_style = space
indent_size = 3
insert_final_newline = true
trim_trailing_whitespace = true
```

--

## Quelques exceptions

_Les espaces à la fin d'une ligne ont une fonction syntaxique en Markdown_

`.editorconfig`
```
# ...
[*.md]
trim_trailing_whitespace = false
```

--

## Pourquoi trim les espaces?

> On peut cacher les changements d'espaces!

--

```diff
   if true:
        do_something()
-        do_something_else()
+   do_something_else()
```

---

# Type Systems

---

## Conventional Commits

|Prefix|Release|
|---|---|
|fix|patch (0.0.1)|
|perf|patch|
|feat|minor (0.1.0)|
|!/BREAKING CHANGE|major (1.0.0)|
|ci|❎|
|doc|❎|
|style|❎|
|test|❎|

https://www.conventionalcommits.org/en/v1.0.0/

--

## Conventional Commits

- [Commitizen](https://commitizen.github.io)

- [Commitlint](https://commitlint.js.org)