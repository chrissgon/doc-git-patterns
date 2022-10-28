# Git Patterns

Padrões para projeto GIT, como fluxo de branches e modelos de commit.

## Conventional Commits

O desenvolvimento utilizando Git é comum para qualquer desenvolvedor.

Para manter um padrão conciso o Conventional Commits sugere o modelo:

``` bash
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

Os significados de cada elemento são:

`type:` Caracteriza a natureza da mudança. Tem como valores padrões:
- `feat`
- `fix`
- `docs`
- `style`
- `refactor`
- `perf`
- `test`
- `build`
- `ci`
- `chore`
- `revert`

`scope:` Contextualiza o commit, podendo informar branches, arquivos ou funções.

`description:` Descrição curta do commit. É recomendado utilizar o imperativo ao invés do pretérito. O intuito seria descrever **o que fará caso aplicado**, dessa forma a expressão - *Caso aplicado irá criar dashboard de casos* - descreve melhor que - *Caso aplicado irá criação de dashboard de casos*.

`body:` Descrição longa do commit. Contextualiza com mais informações o `description`.

`footer:` Rodapé do commit, normalmente informa uma BREAKING CHANGE em concordância com o [SemVer](https://semver.org/). O objetivo é alertar e descrever a incompatibilidade com a versão anterior. Caso não haja uma BREAKING CHANGE, ainda se pode informar usando outra convenção, como [git trailer](https://git-scm.com/docs/git-interpret-trailers).

Exemplos:

- Commit simples
``` bash
docs: correct spelling of CHANGELOG
```
- Commit com escopo
``` bash
feat(lang): add Polish language
```
- Commit com descrição longa
``` bash
fix: prevent racing of requests

Introduce a request id and a reference to latest request. Dismiss
incoming responses other than from latest request.
```
- Commit com rodapé BREAKING CHANGE
``` bash
feat: allow provided config object to extend other configs

BREAKING CHANGE: `extends` key in config file is now used for extending other config files
```
- Commit com rodapé
``` bash
refactor: change createUser() logs

Reviewed-by: Admin
Refs: #123
```

## Commitlint & Commitizen

Para facilitar a adoção do Conventional Commits, se sugere utilizar o [Commitlint](https://commitlint.js.org/#/) ou [Commitizen](https://github.com/commitizen/cz-cli). Eles fornecem uma CLI que auxilia a aderência da convenção.

## Git Flow

O Git Flow é um modelo de ramificação que proporciona maior controle sobre o código fonte.

O modelo sugere o seguinte fluxo:

![Git Flow Schema]("./gitflow.png")

Para facilitar a implementação do fluxo o Git Flow disponibiliza uma [CLI](https://danielkummer.github.io/git-flow-cheatsheet/index.pt_BR.html).

## Referências
- [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/)
- [Medium - Conventional Commits Pattern](https://medium.com/linkapi-solutions/conventional-commits-pattern-3778d1a1e657)
- [Commitlint](https://commitlint.js.org/#/)
- [Commitizen](https://github.com/commitizen/cz-cli)
- [Semantic Versioning](https://semver.org/)
- [Cheatsheet Git Flow](https://danielkummer.github.io/git-flow-cheatsheet/index.pt_BR.html)
- [Git Flow Atlassian](https://www.atlassian.com/br/git/tutorials/comparing-workflows/gitflow-workflow)

---
Desenvolvido por [Christopher Gonçalves](https://github.com/chrissgon)
