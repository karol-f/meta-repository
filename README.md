# META repository
----
This project is based on the Meta package and features multi GIT repositories which can be auto-linked for easy workflow.
For detailed explanation on how things work, checkout the [documentation](https://github.com/mateodelnorte/meta)

## Getting Started

```js
yarn install
yarn setup // this will:
           // - execute 'yarn meta-git update' - to pull from Git all repositories defined in .meta file
           // - execute 'yarn meta-git checkout develop' - to change all branches to develop (if repository has such branch)
           // - execute 'yarn meta-yarn install' to install all dependencies in subfolders
           // - execute 'yarn meta-yarn link --all' to symlink necessary dependencies
```

## Pushing changes to shared library

You will need this point only AFTER developement. The 'Getting started' instructions set everything up, so that you can develop shared library instantly. 

But if you want to share the results and make it permament, push your changes in shared library to git, normal way, then execute: 

```js
yarn meta-bump-yarn shared-library
``` 

This command will auto git-tag last commit and update correct tag version in package.json files of e.g. consumer-library.

## Workflow

You can link all packages (subfolders) to easy work with them without need of repositories to update it's dependencies in package.json:

```js
yarn meta-yarn link --all
```

This command is auto executed after `yarn setup`, so you have to use `yarn meta-yarn link --all` (in root directory of meta-repository) only in case of symlink (e.g. `consumer-library/node_modules/shared-library`) overwrite.
# shared-library
