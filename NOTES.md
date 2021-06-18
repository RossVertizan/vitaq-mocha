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

This will run the test and build process.

### How to install

Installed as part of wdio-vitaq-mocha-framework:

```node
npm install @wdio/vitaq-mocha-framework@<version> --registry http://localhost:4873 --save-dev
```

or manually with:

```node
npm install vitaq-mocha@<version> --registry http://localhost:4873 --save-dev
```

### Changes made to facilitate vitaq-mocha

#### Options

- showMochaDetails - Prints a banner to prove we are using vitaq-mocha and shows version number
- standardMocha: true - switches to default Mocha mode - used in the testing
- cleanReferencesAfterRun - now defaults to false, set to true to avoid reference being retained
- nextSuiteSelectFunction - the function to call - currently cannot be reached

#### Selector function signature

vitaq.nextActionSelector(suite, curr);

### TODO LIST

1. Need to add error/exception handlin capability for tests that fail in Mocha. Need to make sure we don't leave the Vitaq end hanging.
