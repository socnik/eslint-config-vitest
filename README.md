# ESLint Config Vitest

Strict config for [`eslint-plugin-vitest`](https://github.com/veritem/eslint-plugin-vitest). You can see config in [`src/index.js`](https://github.com/socnik/eslint-config-vitest/tree/main/src/index.js).

## Usage

**This config uses [flat config format](https://eslint.org/blog/2022/08/new-config-system-part-2), so ESLint v9+ required.**

Install packages:

```shell
npx nypm add -D eslint eslint-plugin-vitest @socnik/eslint-config-vitest
```

Add to your ESLint config:

```js
// ...
import vitest from 'eslint-plugin-vitest'
import { vitestConfig } from '@socnik/eslint-config-vitest'
// ...

export default [
  // ...
  {
    ...vitestConfig, // Add Vitest rules preset. Add onto top!
    name: 'Vitest tests',
    files: ['src/**/*.test.ts'],
    plugins: {
      vitest, // Add Vitest plugin
    },
    rules: {
      'vitest/prefer-todo': 'off', // Override rules if you want to change something
    },
  },
  // ...
]
```
