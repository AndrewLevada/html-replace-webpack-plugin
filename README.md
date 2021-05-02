# [html-replace-webpack-plugin] fork

An upgraded version of Webpack plugin that replaces HTML contents with custom pattern string or regex.

For more information visit documentation of original plugin: [html-replace-webpack-plugin]

## Changes

Replacement function now provides a relative path of a currently edited file. 

```javascript
var webpack = require('webpack')
var HtmlReplaceWebpackPlugin = require('html-replace-webpack-plugin')

module.exports = {
  plugin: [
    new HtmlWebpackPlugin({
      /* configs */
    }),
    new HtmlReplaceWebpackPlugin([
      {
        pattern: /Hello world/g,
        replacement: function(match, filePath, groups) {
          return `Goodbye world at ${filePath}`;
        }
      }
    ])
  ]
}
```
