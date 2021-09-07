---
## 26/03/2021
### 15:21

`npm publish --registry http://localhost:4873`

#### Changes made to facilitate vitaq-mocha

##### Options

- showMochaDetails - Prints a banner to prove we are using vitaq-mocha and shows version number
- standardMocha: true - switches to default Mocha mode - used in the testing
- cleanReferencesAfterRun - now defaults to false, set to true to avoid reference being retained
- nextSuiteSelectFunction - the function to call - currently cannot be reached

##### Selector function signature

vitaq.nextActionSelector(suite, curr);


---## 07/09/2021

### 13:53

OK, how to update this repo to be in sync with the latest version of mocha

---

> #### Here are the instructions from Christian Bromann for the Webdriverio development
>
> Instructions from Christian for creating a branch:
> https://github.com/webdriverio/webdriverio/pull/6638#issuecomment-810319601
>
> @RossVertizan I recommend to throw away your main branch and start working on the upstream one, here is how you do it:
>
> ```text
> $ git checkout main
> $ git checkout -b old_main
> $ git branch -D main
> $ --- git remote add upstream git@github.com:webdriverio/webdriverio.git ---
> $ git remote add upstream git://github.com/webdriverio/webdriverio.git
> $ git fetch --all
> $ git checkout upstream/main
> $ git checkout -b main
> ```
>
> Then before you start working on anything, pull from upstream and create a new branch:
>
> ```text
> $ git checkout main
> $ git pull origin main
> $ git checkout -b my_new_branch
> ```

---
