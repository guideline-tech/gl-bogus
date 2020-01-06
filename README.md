# gl-bogus

## Requirements for Guideline Engineers

* Create or have access to github account
* Authenticate with Github


### Authenticating with Github

You will need to create a personal access token in your personal Github account.

https://help.github.com/en/github/managing-packages-with-github-packages/configuring-npm-for-use-with-github-packages

```
GDL-122% npm login --registry=https://npm.pkg.github.com
Username: markehost
Password:
Email: (this IS public) mark.e.host@gmail.com
Logged in as markehost on https://npm.pkg.github.com/.
```



### Publishing a Package

https://help.github.com/en/github/managing-packages-with-github-packages/configuring-npm-for-use-with-github-packages#publishing-a-package

You will first need to authenticate as a user in order to properly publish.

This is a potentially dangerous action and should be guarded.  We may also want to set explicit versions for our own packages so that we upgrade manually rather than taking in the latest and potentially pulling in bugs.



<!-- {
  "name": "@guideline-tech/gl-bogus",
  "version": "1.0.0",
  "repository": "git://github.com/guideline-tech/gl-bogus.git",
  "devDependencies": {
    "lerna": "^3.20.2"
  }
} -->


<!-- "repository": {
    "type": "git",
    "url": "git://github.com/guideline-tech/gl-bogus.git",
    "directory": "packages/name"
  } -->

### TODO: 

* Workflow for pushing to git and publishing to packages.
* Pre-publish hook for building the JS before `npm publish`.
* Pre-commit hook to check linters.
