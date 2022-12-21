# Pre-commit hook for typescript type checking

This is a hook for [pre-commit](https://github.com/pre-commit/pre-commit) linting your gherkin BDD tests with [gherkin-lint](https://github.com/vsiakka/gherkin-lint).

### Usage

- To use this you first need to install pre-commit.
- Then create a pre-commit config file in the root of your project.
- Run `pre-commit install` from the root of your project

Finally add this to your `.pre-commit-config.yaml`:

```yaml
- repo: git://github.com/ggozad/gherkin-check
  rev: "" # Use the sha or tag you want to point at
  hooks:
    - id: gherkin-check
```

Now everytime you commit a `.feature` file `gherkin-lint` will run on the file.

By default, `gherkin-lint` expects to find the configuration file `.gherkin-lintrc` in the root of your project. If you want to use a different configuration file you can do:

```yaml
- repo: git://github.com/ggozad/gherkin-check
  rev: "" # Use the sha or tag you want to point at
  hooks:
    - id: gherkin-check
      args: [--config, path/to/config]
```
