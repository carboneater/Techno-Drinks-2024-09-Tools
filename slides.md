---
theme: seriph
background: https://source.unsplash.com/collection/94734566/1920x1080
class: text-center
hideInToc: true
highlighter: shiki
lineNumbers: true
drawings:
  persist: false
transition: slide-left
mdc: true
---

# Outils pour se Simplifier le Développement

---
hideInToc: true
---

# $ whoami

- Présentateur récidiviste
- Dev & Ops
- Paresseux
- <3 Outils

---
hideInToc: true
---

# ToC

<Toc minDepth="1" maxDepth="1"></Toc>

---
transition: slide-up
---

# Methodologie

- F/LOSS
- Utile

---
level: 2
---

# Disclaimer

YMMV

---
layout: section
---

# IDEs

---
level: 2
---

# VSCode
|`.vscode/`||
|---|---|
|`extensions.json`|Recommandations d'extensions|
|`launch.json`|Débugging|
|`settings.json`|Configuration IDE/Extensions|

---
level: 2
transition: slide-up
---

# EditorConfig

`.editorconfig`
``` {all|4|8|9-10|11|12|all}
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

---
level: 3
transition: slide-up
---
## Quelques exceptions

_Les espaces à la fin d'une ligne ont une fonction syntaxique en Markdown_

`.editorconfig`
```
# ...
[*.md]
trim_trailing_whitespace = false
```

---
level: 3
---

## Pourquoi trim les espaces?

> On peut cacher les changements d'espaces!

C'est cool, sauf qu'en Python...
```diff
   if true:
        do_something()
-        do_something_else()
+   do_something_else()
```

---
layout: section
---

# Types

---
layout: two-cols
level: 2
---

JS
```js {monaco-run}
const add = (a,b) => a+b

console.log(add(1,2))
```

::right::
TS
```ts {monaco-run}
const add = (a: number,b: number) => a+b

console.log(add(1,2))
```

---
level: 2
---

# Zod: Input Parsing, Typing & Validation

```ts twoslash
import {z} from 'zod'

// Describe Object
const schema = z.object({
  id: z.number().min(1),
  name: z.string()
})

console.log(schema.parse({
  id: 2,
  name: 'test',
  malicious: 'EICAR!'
}))
/* { id: 2, name: 'test'} */
```

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

---
layout: section
---

# Observabilite

---
level: 2
---

# La tente Grafana

- Dashboards: Grafana
- Logs: Loki
- Metriques: Prometheus
- Traces: Tempo

---
level: 2
---

# Instrumentation: OpenTelemetry

- Probablement disponible dans votre language
- Contient de nombreuses instrumentations automatiques
- Facile a integrer

---
layout: section
---

# Presentation

---
layout: two-cols-header
level: 2
---

# WYSIWYM

::left::

# [VSCode-Reveal](https://www.evilznet.com/vscode-reveal/#/)

- Markdown
- Simple!
- Beau formattage de code

::right::

# [Slidev](https://sli.dev)

- Markdown
- Plus Complexe
- Code interactif!

---
layout: section
---

# Conclusion

Il y a probablement deja un outil pour faire ca

Embrassez votre cote paresseux!

