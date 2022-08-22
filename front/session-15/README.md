# Session15
(1401/05/31)

## Webpack

 webpack is a static module bundler for modern JavaScript applications.
 [link](https://webpack.js.org/concepts/)
### Entry

 - An entry point indicates which module webpack should use to begin building out its internal dependency graph. 
 - By default its value is ./src/index.js

 `
 module.exports = {
  entry: './path/to/my/entry/file.js',
 };
 `
 
### Output

 - The output property tells webpack where to emit the bundles it creates and how to name these files. 
 - It defaults to ./dist/main.js
 `
 const path = require('path');

 module.exports = {
  entry: './path/to/my/entry/file.js',
  output: {
    path: path.resolve(__dirname, 'dist'),
    filename: 'my-first-webpack.bundle.js',
    },
  };
 `
 
 1- output.filename : to tell webpack the name of our bundle
 2- output.path : where we want it to be emitted to
 
### Loaders
  - Loaders allow webpack to process other types of files and convert them into valid modules that can be consumed by your application and added to the dependency graph.
  - loaders have two properties :
  1- test :  identifies which file or files should be transformed.
  2- use : indicates which loader should be used to do the transforming.
  [Loaders list](https://webpack.js.org/loaders/https://webpack.js.org/loaders/)
  
  `
  const path = require('path');

  module.exports = {
	  output: {
	    filename: 'my-first-webpack.bundle.js',
	  },
	  module: {
	    rules: [{ test: /\.txt$/, use: 'raw-loader' }],
	  },
  };
  `
### Plugins
 - plugins can be leveraged to perform a wider range of tasks like bundle optimization, asset management and injection of environment variables.
 - In order to use a plugin, you need to require() it and add it to the plugins.
 [Plugins list](https://webpack.js.org/plugins/)
 
 `
 const HtmlWebpackPlugin = require('html-webpack-plugin');
 const webpack = require('webpack'); //to access built-in plugins

 module.exports = {
  module: {
    rules: [{ test: /\.txt$/, use: 'raw-loader' }],
  },
  plugins: [new HtmlWebpackPlugin({ template: './src/index.html' })],
 };
 ` 
 
### Mode
 -  you can enable webpack's built-in optimizations that correspond to each environment. 
 - development, production or none
 `
 module.exports = {
  mode: 'production',
 };
 `
 
