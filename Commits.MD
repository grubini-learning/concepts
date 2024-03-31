# Commits

Easy set of rules on commit history, which makes it easier to write automated tools on top of.

## Structure

\<type>[scope?]: \<description>
[body?]
[footer?]

### types

- fix: patches a bug (PATCH SEMANTIC VERSIONING)
- feat: new feature (MINOR SEMANTIC VERSIONING)
- BREAKING CHANGE or by adding a !: breaking change (MAJOR SEMANTIC VERSIONING)
- @\<other-types>

  - build:
  - chore:
  - ci:
  - docs:
  - style:
  - refactor:
  - perf:
  - test:

  ### scopes

  Must consist of a noun describing a section of a codebase

  ### description

  Must follow the colon and space after the `type/scope`. Short summary of the code changes.

  ### footer

  Must use `-`

  **Example** `feat(lang): add Polish language`

  ### Resources

  [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/)
