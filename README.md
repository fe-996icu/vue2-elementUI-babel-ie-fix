# vue2-elementUI-babel-ie-fix
解决vue2.x和ElementUI工程使用babel转换后在IE浏览器报错问题

> #### `babel`转换后还是报错，可能是`ElementUI`组件库的`js`未经过`babel`转换导致的，将`ElementUI`组件库的`js`路径添加到`/build/webpack.base.conf.js`文件中`babel-loader`中经过`babel`转换即可解决。

```javascript
...
module.exports = {
  ...
  module: {
    rules: [
      ...
      {
        test: /\.js$/,
        loader: 'babel-loader',
        include: [
          resolve('src'), 
          resolve('test'), 
          resolve('node_modules/webpack-dev-server/client'),
          resolve('node_modules/element-ui/src'),
          resolve('node_modules/element-ui/packages')
        ]
      },
      ...
    ]
  },
  node: {
    ...
  }
}
```
