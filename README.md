## Summary

We decided to use airbnb style guide

- https://github.com/airbnb/javascript

#### Pros

- No need to create our own
- Easier to learn when code looks familiar
- Easier to review code
- Has plugin support for VS, vim and eslint
- Rules seems very similar to what we already have in hapi-starter-kit

#### Cons

- Bad for people who only eat at Burger King.

## Add airbnb packages

Add airbnb dependecies for development.

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

## To use

- Run lint to find any inconsistencies

```
npm run lint
```

- Automatically fix anything that can be fix automatically

```
npm run lint --cache --fix
```

## Run linting on commit

- We want to run lint before we commit but we don't want to lint the whole repo.
- We want to lint only the changed files. So we use lint-staged. This will add more packages and modify your package.json.

```
npx mrm lint-staged
```

- It seems that we need to modify package.json and remove `--fix` option from `lint-staged` to prevent autofixing issues

```
npx mrm lint-staged
```

## FAQ
- What if I really need to NOT follow style guide.  
  - https://eslint.org/docs/2.13.1/user-guide/configuring#disabling-rules-with-inline-comments

## Add Prettier
- Prettier does more formatting than linting

```
npm install --save-dev eslint-plugin-prettier
npm install --save-dev eslint-config-prettier
npm install --save-dev --save-exact prettier
```

#### Modify .eslintrc
```
module.exports = {
      "extends": ["airbnb-base", "plugin:prettier/recommended"]
};
```

#### Add prettier rules
- create .prettierrc
```
{
  "arrowParens": "always",
  "semi": true,
  "useTabs": false,
  "tabWidth": 2,
  "bracketSpacing": true,
  "singleQuote": true,
  "jsxBracketSameLine": false,
  "printWidth": 180
}
```

## Links
- https://www.npmjs.com/package/eslint-config-airbnb-base
- https://github.com/okonet/lint-staged#readme
- https://github.com/typicode/husky#readme
- https://github.com/prettier/eslint-plugin-prettier#readme
