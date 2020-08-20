# Installation

1. Navigate to your app directory where you want to include this style configuration.

   ```bash
   cd my-app
   ```

2. Run this command inside your app's root directory. Note: this command executes the `eslint-prettier-airbnb-node.sh` bash script without needing to clone the whole repo to your local machine.

   ```bash
   exec 3<&1;bash <&3 <(curl https://raw.githubusercontent.com/Hfreitas/eslint-prettier-airbnb-node/master/eslint-prettier-airbnb-node.sh 2> /dev/null)
   ```

3. Make selections for your preference of package manager (npm or yarn), file format (.js or .json), max-line size, and trailing commas (none, es5, all).

4. Look in your project's root directory and notice the two newly added/updated config files:
   - `.eslintrc.js` (or `.eslintrc.json`)
   - `.prettierrc.js` (or `.prettierrc.json`)

# Packages

### Main Packages

1. [ESlint](https://eslint.org/)
2. [Prettier](https://prettier.io/)

### Airbnb Configuration

1. [eslint-config-airbnb-base](https://www.npmjs.com/package/eslint-config-airbnb-base)
   - This package provides Airbnb's .eslintrc as an extensible shared config, don't contains JSX rules.

### ESlint, Prettier Integration

1. [eslint-plugin-prettier](https://github.com/prettier/eslint-plugin-prettier)
   - Runs Prettier as an ESLint rule and reports differences as individual ESLint issues.
2. [eslint-config-prettier](https://github.com/prettier/eslint-config-prettier)
   - Turns off all rules that are unnecessary or might conflict with Prettier.

# Created Configuration Files

Once files are created, you may edit to your liking.

### eslintrc(.js/.json)

- [more info](https://eslint.org/docs/user-guide/configuring)

```
{
"plugins": [
    "prettier"
  ],
  "extends": [
    "airbnb-base",
    "plugin:prettier/recommended",
  ],
  "env": {
    "browser": true,
    "commonjs": true,
    "es6": true,
    "es2020": true,
    "jest": true,
    "node": true
  },
  "rules": {
    "max-len": [
      "warn",
      {
        "code": '${max_len_val}',
        "tabWidth": 2,
        "comments": '${max_len_val}',
        "ignoreComments": false,
        "ignoreTrailingComments": true,
        "ignoreUrls": true,
        "ignoreStrings": true,
        "ignoreTemplateLiterals": true,
        "ignoreRegExpLiterals": true
      }
    ]
  }
}
```

### prettierrc(.js/.json)

- [more Info](https://prettier.io/docs/en/configuration.html)

```
{
"printWidth": (SET BY USER),
  "singleQuote": true,
  "trailingComma": (SET BY USER)
}
```

---

This script and README is a modified copy of Paulo Ramos eslint-prettier-airbnb-react setup script[tutorial](https://github.com/paulolramos/eslint-prettier-airbnb-react).
