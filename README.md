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

## Core questions

### `changesets`

When true, it will create a GitHub workflow for [Atlassian Changesets](https://github.com/changesets/changesets)

If the package.json exists, it will automatically add a required dependency. Otherwise make sure to add it yourself, for example as

```
yarn add @changesets/cli
```

### `release_with_changesets`

Extends the changesets workflow to also automatically push NPM packages when release PRs are merged.

**You may have to manually add a `release` script to you package.json if it did not exist when initializing the template**

```json
{
  "scripts": {
    "release": "changeset publish"
  }
}
```

### `auto_tag`

Asked when `release_with_changesets` is `false`, adds a GitHub workflow to automatically create tags when chagesets package.json version changes.
