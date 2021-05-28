# fish-shop/install-plugin-manager

[![Tests Status](https://github.com/fish-shop/install-plugin-manager/actions/workflows/test.yml/badge.svg)](https://github.com/fish-shop/install-plugin-manager/actions?query=workflow%3Atests) [![License](https://img.shields.io/badge/license-MIT-blue)](http://opensource.org/licenses/mit-license.php) [![fish](https://img.shields.io/badge/fish-3.2.2-blue)](https://fishshell.com) [![Issues](https://img.shields.io/github/issues/fish-shop/install-plugin-manager)](https://github.com/fish-shop/install-plugin-manager/issues)

A GitHub action for installing a [fish shell](https://fishshell.com) plugin manager.

## Prerequisites

This action requires the [fish shell](https://fishshell.com). You can install it using the [fish-actions/install-fish](https://github.com/fish-actions/install-fish) action.

## Usage

Add a suitable `uses` step to your GitHub [workflow](https://docs.github.com/en/actions/reference/workflow-syntax-for-github-actions) and specify the plugin manager to be installed by providing a value for the `plugin-manager` input as shown below:

```yaml
- name: Install Fisher plugin manager
  uses: fish-shop/install-plugin-manager@v1
  with:
    plugin-manager: fisher
```

## Supported plugin managers

The following table lists the supported plugin managers and the corresponding `plugin-manager` input value to use in your workflow:

| Plugin manager                                         | `plugin-manager` value |
|--------------------------------------------------------|------------------------|
| [Fisher](https://github.com/jorgebucaran/fisher)       | `fisher`               |
| [Oh My Fish](https://github.com/oh-my-fish/oh-my-fish) | `oh-my-fish`           |
| [plug.fish](https://github.com/kidonng/plug.fish)      | `plug.fish`            |

## Managing plugins

After installing one of the supported plugin managers listed above, you may interact with it directly in subsequent steps of your workflow to install, remove, and manage plugins as desired.

For example, to install the [Pond](http://github.com/marcransome/pond) plugin using [Fisher](https://github.com/jorgebucaran/fisher):

```yaml
- name: Install Pond plugin with Fisher
  run: fisher install marcransome/pond
  shell: fish {0}
```

Refer to the official documentation for the specific plugin manager being used for additional information.

## Action versions

Use one of the following patterns when specifying the version reference for this action in your workflow (i.e. the `{ref}` value in `uses: fish-shop/install-plugin-manager@{ref}`):

* The major version tag (e.g. `v1`) - will always point at the latest `v1.*` release and will include non-breaking changes and bug fixes
* The minor version tag (e.g. `v1.1`) - will always point at the latest `v1.1.*` release and will include bug fixes
* The patch version tag (e.g. `v1.1.0`) - will always point at the `v1.1.0` release
* The branch reference `main` - will include the latest changes from the `main` branch
* A specific commit SHA (e.g. `c3aad46b6014e86ab163e323bdfc79c987de0eba`)

The recommended form is `vX` (e.g. `v1`). This will ensure that the version of the action used in your workflow includes the latest non-breaking changes and bug fixes, and guarantees compatibility with previous versions of that major release number.

Referencing `main` in your workflow is _not_ recommended as this branch may include breaking changes intended for the next major release.

## License
`fish-shop/install-plugin-manager` is provided under the terms of the [MIT License](http://opensource.org/licenses/mit-license.php).

## Contact
Email me at [marc.ransome@fidgetbox.co.uk](mailto:marc.ransome@fidgetbox.co.uk) or tweet [@marcransome](http://www.twitter.com/marcransome).
