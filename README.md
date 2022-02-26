# Copier templates for common GitHub config

## Usage

### Installing

Use the `copy` command to add to an existing repo

```
copier -a .copier-github.yaml copy https://github.com/tpluscode/github-copier-template.git .
```

### Updating

```
copier -a .copier-github.yaml update
```

## Answers

### `changesets`

When true, it will create a GitHub workflow for [Atlassian Changesets](https://github.com/changesets/changesets)

**Remember to manually add a `release` script to you package.json**

```json
{
  "scripts": {
    "release": "changeset publish"
  }
}
```
