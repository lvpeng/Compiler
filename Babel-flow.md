# Babel Docs Note && QA
- how can i know if current envirement support certain feature?

- Babel how to compile ?
e.g.
```js
[1,2,3].map(n => n + 1);
```
how to compile to
```js
[1,2,3].map(function(n){
    return n + 1;
})
```

- how to implement a REPL tool ?

- core package：
  - babel-core
  - babylon
  - babel-traverse
  - babel-generator

The compiler can be broken down into 3 parts:

  - The parser: babylon
  - The transformer[s]: All the plugins/presets
  - These all use babel-traverse to traverse through the AST
  The generator: babel-generator
### babel flow
The flow looks like this:
> input string -> parser (babylon) -> AST -> transform (babel-core) -> AST ->  babel-generator -> output string

### babel-core是Babel的最核心package，相当于Babel的大心脏，负责对ES2015代码进行编译环节:
- index.js -> module.exports = require('./lib/api/node.js')
  - 引入lib/api/node.js
  - node.js 代码解读
    - 自定义exports属性
    | 属性 | 值  |  说明  |       
    | :------:| :------: | :--:|
    | _esModule | true |  |
    | transformFromAst | undefined | |
    | transform | undefined | |
    | analyze | undefined | |
    | Pipeline | undefined | |
    | OptionManager | undefined | |
    | traverse | undefined | |
    | types    | undefined | |
    | message    | undefined | |
    | util    | undefined | |
    | version    | undefined | |
    | resolvePreset    | undefined | |
    | resolvePlugin    | undefined | |
    | template    | undefined | |
    | buildExternalHelpers    | undefined | |
    | options    | undefined | |
    | File    | undefined | |
    - Object.defineProperty 方法 :By default, values added using this are **immutable**.

- 向外暴露了babel.transform方法
-
