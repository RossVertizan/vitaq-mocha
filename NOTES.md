<!-- markdownlint-disable -->

### How to sync with original mocha

The original Git repository is listed as a remote

```shell
git remote -v
```

#### Steps to sync with original

1. Make sure that everything is committed in the local repo - `git status`
2. Check the branch - `git branch -v`
3. Fetch the upstream changes (from the original repo) - `git fetch upstream`
4. Pull from the upstream to the branch - `git pull upstream master`
5. Go through the merge process and resolve any conflicts
6. Run the pre-publish checks - `npm run prepublishOnly`
7. When all checks passing can be committed and published.
8. Perform standard Vitaq end-to-end tests with this installed to make sure everything is working as expected
9. Update the comment in the README.md about the latest merge version

##### Notes on above

1. Had to use:

```shell
git config --global url."https://".insteadOf git://
```

before the `git fetch upstream` would [work.](https://stackoverflow.com/questions/16298986/unable-to-connect-to-github-com-for-cloning)

### How to publish

#### Commit

Commit the changes

#### Tag

Update the version number

```node
npm version <version number>
```

#### Publish

Then publish to the registry:

```node
npm publish --registry http://localhost:4873
```

Can also publish to the cloud repository:

```node
npm publish --registry https://pkgs.vitaq.online
```

Or to the NPM registry for public availability

```node
npm publish --registry https://registry.npmjs.org
```

This will run the test and build process.

### How to install

Installed as part of wdio-vitaqai-mocha-framework:

```node
npm install wdio-vitaqai-mocha-framework@<version> --registry http://localhost:4873 --save-dev
```

or manually with:

```node
npm install vitaqai-mocha@<version> --registry http://localhost:4873 --save-dev
```

### Changes made to facilitate vitaqai-mocha

#### Options

- showMochaDetails - Prints a banner to prove we are using vitaqai-mocha and shows version number
- standardMocha: true - switches to default Mocha mode - used in the testing
- cleanReferencesAfterRun - now defaults to false, set to true to avoid reference being retained
- nextSuiteSelectFunction - the function to call - currently cannot be reached

#### Selector function signature

vitaq.nextActionSelector(suite, curr);

### TODO LIST

1. Need to add error/exception handlin capability for tests that fail in Mocha. Need to make sure we don't leave the Vitaq end hanging.
