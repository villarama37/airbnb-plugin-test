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

## TODO:  
- Run eslint before committing code
- Add prettier
