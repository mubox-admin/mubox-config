# @mubox/eslint-config & @mubox/tsconfig

Mu ESLint config
木的项目代码自用规范
vue参考Element-Plus
react参考Ant-design

## Install

### Vue

```bash
pnpm i eslint prettier @mubox/eslint-config-vue @mubox/ts-config -D 
```

Need `tsconfig.json` presented and `typescript` installed as devDependencies.

```json
// package.json
{
  "eslintConfig": {
    "extends": ["@mubox/vue"]
  }
}
```

### React

```bash
pnpm i eslint prettier @mubox/eslint-config-react @mubox/ts-config -D 
```

```json
// package.json
{
  "eslintConfig": {
    "extends": ["@mubox/react"]
  }
}
```

### script

```json
    "lint": "eslint . --ext .vue,.js,.ts,.jsx,.tsx,.md,.json --max-warnings 0 --cache",
    "lint:fix": "pnpm run lint --fix",
    "lint:commit": "commitlint --from $(git merge-base origin/dev HEAD) --to HEAD > ./commit-lint.txt",
```

### .prettierrc

- 配置 prettierrc

```json
{
  "printWidth": 100,
  "proseWrap": "never",
  "htmlWhitespaceSensitivity": "ignore",
  "endOfLine": "auto",
  // 下面是默认设置
  "tabWidth": 2,
  "useTabs": false,
  "singleQuote": false,
  "semi": true,
  "vueIndentScriptAndStyle": false,
  "quoteProps": "as-needed",
  "bracketSpacing": true,
  "trailingComma": "es5",
  "jsxSingleQuote": false,
  "arrowParens": "always",
  "insertPragma": false,
  "requirePragma": false
}
```

### tsconfig.json

```json
{
  "$schema": "https://json.schemastore.org/tsconfig",
  "extends": "@mubox/ts-config/vue.json",
  "compilerOptions": {
    "baseUrl": ".",
    "declaration": false,
    "types": ["vite/client"],
    "paths": {
      "@/*": ["src/*"],
    }
  },
  "include": [
    "src/**/*.ts",
    "src/**/*.d.ts",
    "src/**/*.tsx",
    "src/**/*.vue",
    "types/**/*.d.ts",
    "types/**/*.ts",
    "vite.config.ts"
  ],
  "exclude": ["node_modules", "tests/server/**/*.ts", "dist", "**/*.js"]
}
```
