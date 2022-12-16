---
title: "設置專案"
date: 2022-12-13T14:46:54+08:00
weight: 20
---

- [Vite Server Proxy](#vite-server-proxy)
- [Linting/Formating](#lintingformating)
  - [.eslintrc.js](#eslintrcjs)
  - [.prettierrc.js](#prettierrcjs)
- [Reference](#reference)

## Vite Server Proxy
打開 vite.config.js，找到 server，以下設置會使 `axios.get('/api/A')` 等價於 `axios.get('http://localhost:4567/api/A')`，避免開發時會遇到的跨域問題。
```js
  server: {
    port: 3000,
    proxy: {
      // http://localhost:3000/api -> http://localhost:4567api/
      '/api': 'http://localhost:4567',
    }
  },
```

## Linting/Formating
### .eslintrc.js  
```js
module.exports = {
  extends: ["plugin:vue/essential", "eslint:recommended", "@vue/prettier"],
  parserOptions: {
    parser: "babel-eslint"
  },
  rules: {
    semi: ["error", "always"],
    "no-console": "off"
  }
};
```
### .prettierrc.js  
```js
module.exports = {
  semi: false,
  singleQuote: true,
  arrowParens: "avoid"
};
```
## Reference
- [vite-config](https://vitejs.dev/config/)