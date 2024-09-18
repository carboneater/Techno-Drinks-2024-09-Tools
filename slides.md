---
theme: seriph
background: https://source.unsplash.com/collection/94734566/1920x1080
class: text-center
hideInToc: true
highlighter: shiki
lineNumbers: true
drawings:
  persist: false
transition: none
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
layout: section
---

# Objectifs

---

# Méthodologie

- F/LOSS
- Utile
- Facile

---
layout: center
level: 2
---

# Disclaimer

## YMMV

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
   if something:
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

```ts {all|3-6|8-13|all} twoslash
import {z} from 'zod'

const schema = z.object({
  id: z.number().min(1),
  name: z.string()
})

const safeInputs = schema.parse({
  id: 2,
  name: 'test',
  malicious: 'EICAR!'
})
/* { id: 2, name: 'test'} */
```

---
layout: section
---

# SCM/CI

---
layout: two-cols-header
level: 2
---

# Validations

::left::

- Language Server (TS)
- Linter (ESLint)
- Formatter (Prettier)

::right::

- Intégration IDE
- Documentation
- Exécution Automatique
- Performances
- Intégration CI

---
level: 2
---

# Tests!

- Utilisez un Framework!
- Coverage
- Mutation Testing

---
level: 2
---

# Conventional Commits

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

---
level: 2
---

# Conventional Commits

- [Commitizen](https://commitizen.github.io): Plugin IDE

- [Commitlint](https://commitlint.js.org): Validation CI

---
level: 2
---

# CI/CT

- Évitez les dépendances
  - Systèmes
  - Externes
- "Build From Scratch"
  - Reproductibilité
- Lancez les services à l'interne des pipelines

---
level: 2
---

# Semantic-Release

- Version
- Release Notes
- CHANGELOG
- Package
- Tag
- Et bien d'autres!

---
layout: section
---

# Observabilité

---
level: 2
---

# La grande tente Grafana

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
- Facile à intégrer

---
layout: section
---

# Maintenance

---
level: 2
---

# Maintenance

- Renovate
- Dependabot
- OpenRewrite

---
layout: section
---

# Présentation

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

Il y a probablement deja un outil pour faire ca!

Embrassez votre côté paresseux!

Slides: https://github.com/carboneater/Techno-Drinks-2024-09-Tools