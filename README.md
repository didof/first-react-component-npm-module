# How to Reproduce

1. `npm init`
*precautions*: unique package name

2. `npm i -D @babel/cli @babel/core`

3. create `.babelrc`
```json
{
    "presets": ["@babel/preset-react", "@babel/preset-env"]
}
```

4. create the **Componet** in `src/index.js`

5. add a *script* in `package.json`
```json
...
{
    "scripts": {
        "build": "./node_modules/.bin/babel src --out-file index.js"
    },
}
...
```
It reads the code in `src` and transpiles it to ES5 in a new `index.js` file. The latter il located in root.

6. add `react` and `react-dom` both as `devDependencies` and `peerDependencies` in `package.json`
```json
"peerDependencies": {
    "react": "^17.0.1",
    "react-dom": "^17.0.1"
  },
  "devDependencies": {
    "@babel/cli": "^7.12.10",
    "@babel/core": "^7.12.10",
    "@babel/preset-env": "^7.12.11",
    "@babel/preset-react": "^7.12.10",
    "react": "^17.0.1",
    "react-dom": "^17.0.1"
  }
```