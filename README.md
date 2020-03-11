## Add airbnb packages

`npx install-peerdeps --dev eslint-config-airbnb-base`

## Create .eslintrc file

- Create the .eslintrc file with the following

```
module.exports = {
      "extends": "airbnb-base"
};
```

## Add script command in package.json
```
  "scripts": {
        "lint": "eslint --report-unused-disable-directives ."
           },
```

## Run lint on commit
- We want to run lint before we commit but we don't want to lint the whole repo.
- We want to lint only the changed files. So we use lint-staged
```

```

## TODO:  
- Run eslint before committing code
- Add prettier
