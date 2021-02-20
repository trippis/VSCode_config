## LOCAL VS CODE SETUP

### GENERAL EXTENSIONS

1. Bracket Pair Colorizer 2 - Coenraads
2. Material Theme - Mattia Astorino
3. Material Theme Icons - Mattia Astorino
4. Prettier - Prettier

### CSS / HTML5

1. CSS Peek - Pranay Prakash
2. Live Server - Ritwick Dey

### C# and .NET core

1. C# - Microsoft
2. C# FixFormat - Leopotam
3. C# Extensions - JosKreativ
4. Auto-Using for C# - Fudge
5. NuGet Package Manager - jmrog
6. Essential ASP.NET Core Snippets - Will

### SQL

1. SQL Server - Microsoft

### Python

1. Python - Microsoft

### Containers

1. Docker - Microsoft
2. YAML - Red Hat

### JAVASCRIPT

1. ESLint - Dirk Baeumer
2. Angular Snippets (Version 9) - John Papa
3. ES7 React/Redux/GraphQL/React-Native snippets -

### Configuring ESlint, Prettier and Husky

1. Ensure VS Code extensions: ESlint and Prettier are installed.

2. Run project scaffolding:

   - 'npx create-react-app [project_name]'; or
   - 'npm init -y' in a folder

3. From the terminal execute the dev dependencies and include relevant eslint configs and plugins:

a. npm i -D eslint prettier [eslint-config-\*][eslint-plugin-*]

- eslint-config-prettier eslint-plugin-prettier
- eslint-config-node eslint-plugin-node

b. Can also install a well known style guide like airbnb, google etc

- npx install-peerdeps --dev eslint-config-airbnb

4. Create a .eslintrc file in the project root with the following for configs and plugins:

```JSON
   {
      "extends": ["react-app", "airbnb", "prettier", "node"],
      "plugins": ["prettier", "node"],
      "rules": {
      "prettier/prettier": "error",
      "no-unused-vars": "warn",
      "no-console": "off",
      "func-names": "off",
      "no-process-exit": "off"
      }
   }
```

There is a shorthand way of adding the plugin and config support into the "extends" attribute:
"extends": ["react-app", "plugin:prettier/recommended"]

Alternatively, instead of manually creating the above file, ensure eslint is installed globally (npm i -g eslint) then run 'eslint --init' and run through the questions which will create the .eslintrc file.

5. Create a .prettierrc file in the project root and override default settings if you wish as follows:

```JSON
   {
      "rule_name": true or false,
   }
```

6. In VSCode go to user settings (command-, on a mac, control-, on win/linux) and add these settings to the top:

```JSON
   {
      "editor.formatOnSave": true,
      "[javascript]": {
      "editor.formatOnSave": false
   },
      "eslint.alwaysShowStatus": true,
      "prettier.disableLanguages": [
      "js"
      ],
      "files.autoSave": "onFocusChange",
      "editor.codeActionsOnSave": {
      "source.fixAll.eslint": true
      },
   }
```

7. From the terminal initialise the workspace with Git and install Husky and Pretty-Quick:

   - initialise Git -> git init
   - install Husky -> npm i husky lint-staged -D
   - install prett-quick -> npm i pretty-quick -D

8. Go to the projects package.json file and install the Husky hook with this setting in the "scripts" section to format only staged files with prettier just before they are committed:

```JSON
   {
      "scripts": {
      "precommit": "pretty-quick --staged",
      },
   }
```

Reference Links: <br><br>
a. https://www.youtube.com/watch?v=bfyI9yl3qfE&list=FL2OI9Gwq_jHcqoSinBvunrw&index=8 <br><br>
b. https://www.youtube.com/watch?v=SydnKbGc7W8&list=FL2OI9Gwq_jHcqoSinBvunrw&index=1
