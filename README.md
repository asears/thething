# thething

Bots and Actions for GitHub semi-supervised workflows.

This will introduce commits from a workflow directly into a pull request.

Situations where you may want to do this are in tools such as Databricks or Jupyter,  
where running black or ruff may add some steps.  No more local tooling!

## Status

<img alt="badge" src="https://github.com/OWNER/REPOSITORY/actions/workflows/test-ci/badge.svg"/>

## Inspiration

[The Thing](https://en.wikipedia.org/wiki/The_Thing_(1982_film)) is a 1982 American science fiction horror film directed by John Carpenter.

[Jed, as the Dog-Thing](https://en.wikipedia.org/wiki/Jed_(wolfdog)), was a Pacific Northwestern American animal actor.

I  see this style of "save and improve" coding becoming more prevalent with the addition of Copilots and PR Bots.

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
- Additional rules for ruff
- Github Templating

## ruff

Ruff, AStRAL, Charlie Marsh and team

https://github.com/astral-sh/ruff

https://github.com/astral-sh

https://github.com/charliermarsh

https://astral.sh/

## pytest

https://github.com/pytest-dev/pytest

## python

https://www.python.org/doc/versions/

## mermaid

https://github.blog/2022-02-14-include-diagrams-markdown-files-mermaid/

## GitHub Actions

https://github.com/features/actions

https://github.com/actions/github-script

## GitHub Bots

https://github.com/marketplace/actions/github-project-bot
