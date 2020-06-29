# TypeScript setup tutorial

This is a repository to go along with the following article:
https://medium.com/react-graphql-academy/franciscogomes-a-typescript-tale-setup-config-57f8dd4229d0

---

#### Installing the _TypeScript_ compiler globally

```javascript
npm install -g typescript
```

Note: If you’re on macOS and get an “Eaccess” error, try sudo before the npm command.

#### Create a folder for your project and open it

You can either use the macOS Terminal, the Windows Command Line or your IDE, but I’ll use the macOS Terminal

```javascript
mkdir my-first-typescript-project && cd my-first-typescript-project
```

#### Create a file and name it _index.ts_

**\*.ts** is the official extension for _TypeScript_ files and should be always used. It actually stands for _TypeScript_.

```javascript
touch index.ts
```

#### Open your IDE of choice

First, you’ll want to make sure it supports _TypeScript_. You might need to install additional plugin(s). Type the following line in your **index.ts**:

```javascript
console.log("Hello World");
```

At this point, your code hasn’t been compiled to _JavaScript_ yet, therefore your browser won’t be able to read it.

#### In your terminal, type

```javascript
tsc index.ts
```

Note: If you get an error when running the **tsc** command, it means something went wrong with your installation.
Now, look at your file structure and you’ll find a new file **index.js**. This is the compiled file from your _TypeScript_. At the moment is identical since both syntaxes for this code are the same.

#### Create your _tsconfig.json_

```javascript
tsc --init
```

#### Replace your _tsconfig_ content with the following

```javascript
{
  "compilerOptions": {
    "target": "es5" /* Specify ECMAScript target version */,
    "module": "commonjs" /* Specify module code generation */
  }
}
```

---

## Installing _ESLint_

#### Create your _package.json_

```javascript
npm init
```

#### Install dependencies

```javascript
npm install eslint @typescript-eslint/eslint-plugin @typescript-eslint/parser --save-dev
```

#### Create your _.eslintrc.js_ at the root level

You can go for a _json_ file instead

```javascript
touch.eslintrc.js;
```

#### Paste the following code in your _.eslintrc.js_

```javascript
module.exports = {
  parser: "@typescript-eslint/parser",
  extends: ["plugin:@typescript-eslint/recommended"],
  parserOptions: {
    ecmaVersion: 2018,
    sourceType: "module",
  },
  rules: {
    //Our ESlint rules.
  },
};
```

#### Paste the following code in your _index.ts_

```javascript
const name = "Francisco";
const age = 36;
const character = (name: string, age: number): void => {
  console.log(`My name is ${name} My age is ${age}`);
};
```

#### Now let's finally compile

```javascript
tsc index.ts
```

Open your corresponding javascript file, **index.js** and see the compiled version of your code

---

Resources:
[TypeScript](https://www.typescriptlang.org/)
[ESLint](https://eslint.org/)
[@typescript-eslint/eslint-plugin](https://www.npmjs.com/package/@typescript-eslint/eslint-plugin)
[@typescript-eslint/parser](https://www.npmjs.com/package/@typescript-eslint/parser)

Created by [FranciscoMCG](https://github.com/franciscomcg)
