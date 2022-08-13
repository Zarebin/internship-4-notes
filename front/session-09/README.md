# session9(js)
## what is interpertation?
- in interpret code execute line by line
- in compile first source code parsed and then change to AST
- js is a parsed and compiled language
  1. After a program leaves a developer's editor, it gets transpiled by Babel, then packed by Webpack (and perhaps half a dozen other build processes), then it gets delivered in that very different form to a JS engine.
  2. The JS engine parses the code to an AST
  3. Then the engine converts that AST to a kind-of byte code, a binary intermediate representation (IR), which is then refined/converted even further by the optimizing JIT compiler.
  4. Finally, the JS VM executes the program.
![flow of js source program](https://github.com/getify/You-Dont-Know-JS/raw/2nd-ed/get-started/images/fig3.png)
- ** JS is a compiled language.**

