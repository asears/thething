# thething

Bots and Actions for GitHub semi-supervised workflows.

This will introduce commits from a workflow directly into a pull request.

Situations where you may want to do this are in tools such as Databricks or Jupyter,  
where running black or ruff may add some steps.  No more local tooling!

This requires push/pull/synch process with each commit if setup for on push, 
as ruff format and ruff fix may change code.

## Status

### Main
[![test-ci main](https://github.com/asears/thething/actions/workflows/test-ci.yml/badge.svg?branch=main)](https://github.com/asears/thething/actions/workflows/test-ci.yml)

### Workflow Dispatch

[![test-ci PR](https://github.com/asears/thething/actions/workflows/test-ci.yml/badge.svg?event=workflow_dispatch)](https://github.com/asears/thething/actions/workflows/test-ci.yml)

### Push

[![test-ci Push](https://github.com/asears/thething/actions/workflows/test-ci.yml/badge.svg?event=push)](https://github.com/asears/thething/actions/workflows/test-ci.yml)

## Inspiration

[The Thing](https://en.wikipedia.org/wiki/The_Thing_(1982_film)) is a 1982 American science fiction horror film directed by John Carpenter.

[Jed, as the Dog-Thing](https://en.wikipedia.org/wiki/Jed_(wolfdog)), was a Pacific Northwestern American animal actor.

I  see this style of "save and improve" coding becoming more prevalent with the addition of Copilots and PR Bots.

This might turn your commits into a strange E.T. morphing of your intended code.

## Caveats

- This commits to the repo and will change code "on-the-fly" after you commit.
- The unsafe fixes option of ruff additionaly may break code or remove "in-flight" debugging code.
- If you want to revert, the commit will need to be rolled back.
- Having a triggering / branching pattern where this could be run and compared against an existing PR might be beneficial

## Branching Strategies

- If you want to review the code outside of a commit, introducing another PR / branch might be an option.

Example Branching Workflow:

```mermaid
    graph TD;
      A[1. feature/as/my-branch] -->|Pull Request| B[2. thething/mybranch-to-fix];
      B -->|Pull Request| C[3. feature/as/my-branch];
```

Example In-Branch Workflow

```mermaid
    graph TD;
      A[1. feature/as/my-branch] -->|Commit| B[2. feature/as/my-branch];
```

## Improvement Options

- Add some workflow_dispatch conditionals and parameters
- Change the events being used to trigger the actions
- RAG and Web Search API integration
- Path and filename filters
- Additional rules for ruff
- Github Templating
- Auto-generate tests
- Auto-generate docs

## uv

https://astral.sh/blog/uv-unified-python-packaging

https://astral.sh/blog/uv

https://github.com/marketplace/actions/setup-uv

https://docs.astral.sh/uv/guides/integration/pre-commit/

## ruff

Ruff, AStRAL, Charlie Marsh and team

https://github.com/astral-sh/ruff

https://github.com/astral-sh

https://github.com/charliermarsh

https://astral.sh/

## pytest

https://github.com/pytest-dev/pytest

## python

### Setup-Python Action

Versioning of python can be done in pyproject.toml and picked up by the setup-python GitHub action.

.python-version

```plaintext
3.12
```

project `pyproject.toml`

```toml
[project]
requires-python = "${pythonVersion}"
```

poetry `pyproject.toml`

```toml
[tool.poetry.dependencies]
python = "^3.8"
```

https://www.python.org/doc/versions/

https://realpython.com/intro-to-pyenv/

## mermaid

Mermaid and SVG diagrams for markdown and text generation.

https://github.blog/2022-02-14-include-diagrams-markdown-files-mermaid/

## Poetry

https://github.com/search?q=repo%3Aactions%2Fsetup-python%20poetry&type=code

https://stackoverflow.com/questions/75576816/what-do-i-do-when-i-change-poetry-pyproject-toml

Update all packages to latest

```shell
poetry cache clear . --all
rm poetry.lock
poetry install
```

### Editable

https://github.com/orgs/python-poetry/discussions/1135

## Node

https://github.com/npm/node-semver#versions

## GitHub

https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-code-owners

## GitHub Actions

https://github.com/features/actions

https://github.com/actions/github-script

## GitHub Bots

https://github.com/marketplace/actions/github-project-bot

## Nektos Act

https://github.com/nektos/act

## changed-files

https://github.com/tj-actions/changed-files

https://github.com/tj-actions/changed-files/releases

## paths-filter

https://github.com/dorny/paths-filter

https://github.com/dorny/paths-filter/blob/master/CHANGELOG.md

## RAG

https://github.com/pchunduri6/rag-demystified

https://github.com/microsoft/RAG_Hack

https://docs.llamaindex.ai/en/stable/getting_started/starter_tools/rag_cli/

