<pre>================================================================================
                           15:21 - 26/03/2021
================================================================================</pre>

`npm publish --registry http://localhost:4873`

#### Changes made to facilitate vitaq-mocha

##### Options

- showMochaDetails - Prints a banner to prove we are using vitaq-mocha and shows version number
- standardMocha: true - switches to default Mocha mode - used in the testing
- cleanReferencesAfterRun - now defaults to false, set to true to avoid reference being retained
- nextSuiteSelectFunction - the function to call - currently cannot be reached

##### Selector function signature

vitaq.nextActionSelector(suite, curr);
