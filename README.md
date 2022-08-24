# __Checklist Back-end__
This checklist was created to guide me to initialize a new project in Back-end. It was created base on the checklist that a student that study in the same course that I did.

 


# steps


## 1 - Create the project folder;

## 2 - Get inside the folder created in the previous step:
```bash
 npm init -y
```

## 3 - Install the dependencies
```bash 
npm install -D mocha@10.0.0 chai@4.3.6 express@4.17.1 nodemon chai-http@4.3.0
```
## 4 - Create the .gitignore file on the project root
#### write on it:
```bash
/node_modules
```

## 5 - ESLint on project root:
```bash
npm i eslint@6.8.0 eslint-config-trybe-backend@1.0.1 -D
```
This is Trybe's script Lint for the Back-end

```bash
touch .eslintignore .eslintrc.json
```
After create the files we need to write on it

### .eslintignore
```bash
node_modules
```
### .eslintrc.json

```bash
{
  "env": {
    "es2020": true
  },
  "extends": "trybe-backend",
  "rules": {
    "sonarjs/no-duplicate-string": ["error", 5]
  }
}
```

## 6 - Organizing the structure of folders
Create on the project root the **__src__** folder and **__integration__**;

## 7 - In the "__src__" folder add the "__app.js__" file whith:
```bash
// src/app.js
const express = require('express');
const app = express();
module.exports = app;
```

## 8 - In the "__src__" folder add the "__server.js__" file whith:
```bash
// src/server.js
const app = require('./app');
const PORT = process.env.PORT || 3001;
app.listen(PORT, () => console.log('server running on port 3001'));
```

## 9 - Configuring the "__package.json__":
```bash
// package.json
"test": "mocha ./tests/integration --exit"
"start": "node src/server.js",
"dev": "nodemon src/server.js",
"lint": "eslint --no-inline-config --no-error-on-unmatched-pattern -c .eslintrc.json ."
```

## 10 - Commands line that are important:
```bash
npm start
```
This command start the application in case of an error you should start the application again.

```bash
npm run dev
```
This command line initialize the application on the dev environment, then every time you save any file the application is updated.

```bash
npm run test 

//or

npm test
```
These Commands line tests the application

## 11 - Morgan:
```bash
npm i morgan
```

- After it 

```bash

const morgan = require('morgan');
app.use(morgan('dev'));
```

## 12 - CORS:

```bash
npm install cors@2.8
```

- After it;
```bash
const cors = require('cors');
app.use(cors());
```

## 13 - EXPRESS-ASYNC-ERROR
```bash
npm i express-async-error
```

- After it;
```bash
importar ele no "app" depois do "express"
require('express-async-error');
```

