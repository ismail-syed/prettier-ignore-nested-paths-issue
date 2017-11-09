
Install deps:

```
yarn install
```

Run prettier:
```
$ node_modules/.bin/prettier  './**/*.json' --list-different

index.json
nested folder/another/dont-format.json
nested folder/should-format.json
```
Root level `.prettierignore` is respected. Why not the nested, `.some-folder/nested/.prettierignore`?

Expected:
* `some-folder/nested/dont-format.json` not to be listed

Actual:
* `some-folder/nested/dont-format.json` is listed even though it's included a nested `.prettierignore`.
