
### Publishing a Package

https://help.github.com/en/github/managing-packages-with-github-packages/configuring-npm-for-use-with-github-packages#publishing-a-package

You will first need to authenticate as a user in order to properly publish.

This is a potentially dangerous action and should be guarded.  We may also want to set explicit versions for our own packages so that we upgrade manually rather than taking in the latest and potentially pulling in bugs.


---


## Requirements for Guideline Engineers

* Create or have access to github account
* Authenticate with Github





---

### Authenticating with Github

You will need to create a personal access token in your personal Github account in order to create. edit or consumer any package from our Github repo.  This is even required just to use the package since it is a private repo.  Do not add the auth token into the `.npmrc` file (one method of authenticating with NPM).

In a terminal window, run the following command and follow the instructions for auth. 

```
npm login --registry=https://npm.pkg.github.com
```

You will be prompted to enter your `username`, `password` and `email`.  The password will be your `personal access token` that you create in Github.

For more details:

[https://help.github.com/en/github/managing-packages-with-github-packages/configuring-npm-for-use-with-github-packages](https://help.github.com/en/github/managing-packages-with-github-packages/configuring-npm-for-use-with-github-packages)


---


### Lerna Steps to Setup Mono-repo

Note: you should not have to globally install `lerna` and instead always use the `npx lerna ...[commands]` method instead.


1. `npx lerna init` - likely use `independent` mode to manage each package version since they likely won't be in sync like React/React DOM.
2. Add sub-packages into the `packages` directory created from the `init` step.  This could be a copy and paste from somewhere that is already setup as a package, or an `npm init` within the `packages/` directory to start a package from scratch.  If you want a package published it must conform to the NPM standards; needs a `package.json`, a `name`, `version` field, and other optional fields for using the package (`main`, deps, `script` tasks, etc).
3. That is mostly it for now.  The mono-repo is setup at this point.  The next steps will be for versioning and publishing the packages.  There may be additional work for the packages like adding dependencies, setting up `scripts` to run before/after an action, linking dependencies together, etc. See the `commands` within Lerna for options [https://github.com/lerna/lerna/tree/master/commands/](https://github.com/lerna/lerna/tree/master/commands/).


### Versioning with Lerna

First step will always be making changes and committing them.  Lerna will either throw an error if there are any uncommitted changes (after having commited some changes) or exit successfully because the current head is already published (and no changes have been committed).  A new version for a package or set of packages will be required in order to publish.  Otherwise, Lerna will exit out of publish with no changes made to the registry.


1. Run `npx lerna version`.
2. Go through the command prompt for the versions.  If the repo is in `independent` mode it will walk through each package version bump, otherwise, it will bump all packages to the same semver.
3. 

### Publishing with Lerna

1. 
2. 
3. 


<!-- TODO: -->
### Adding a new package with Lerna

1. 
2. 
3. 



### TODO: 

* Workflow for pushing to git and publishing to packages.
* Pre-publish hook for building the JS before `npm publish`.
* Pre-commit hook to check linters.
