# GitHub Actions - PHP Package

Boilerplate workflow for a PHP package.

## Overview

This is a workflow with two jobs:

* Test
* Release

The **Test** job runs on every push and will:

* Install composer dependencies
* Run PHP CS on the `src` and `tests` directories
* Run PHP Unit

The **Release** job runs on the `master` branch, only if the **Test** job runs successfully, and it will:

* Run `semantic-release` to handle the release process

## Setup

This boilerplate assumes a few things:

* The `phpcs` package is installed in the project: `composer require --dev "squizlabs/php_codesniffer=*"`. Our recommended PHP CS configuration can be [found here](https://github.com/ohseesoftware/phpcs-config).
* The `phpunit` package is installed in the project: `composer require --dev phpunit/phpunit`
* The project uses `semantic-release` for the release project. This means you can use a `.releaserc` file in the root of the project to control `semantic-release`.
