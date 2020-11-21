# webpack

### 1day-初识

> 概念：webpack是一个现代JavaScript应用程序的静态资源打包器

+ 四个核心概念

1. 入口

   > entry 入口起点，(entry point)指示webpack应该使用哪个模块，来作为构建其内部依赖图的开始，进入起点后webpack会找出哪些模块和库是入口起点(直接和间接)依赖的。

   ```
   module.exports = {
     entry: './path/to/my/entry/file.js'
   };
   ```

2. 输出

   > 出口(output) output告诉属性告诉webpack在哪里输出它所创建的bundles,以及如何命名这些文件，默认值为./dist文件。

   ```
   const path = require('path');
   
   module.exports = {
     entry: './path/to/my/entry/file.js',
     output: {
       path: path.resolve(__dirname, 'dist'),
       filename: 'my-first-webpack.bundle.js'
     }
   };
   ```

   

3. loader

   > loader让webpack能够处理那些为JavaScript文件(webpack自身只理解JavaScript)。loader可以将所有类型的文件转换为webpack能够处理的有效模块，然后利用webpack自身的打包能力，对它进行处理。
   >
   > 本质上，webpack  loader将所有类型的文件，转换为程序依赖的依赖的依赖图(和最终的bundle)可以直接应用的模块
   >
   > * import 能够导入任何类型的模块，这是webpack的特有的功能  其他的打包程序或任务执行器可能并不支持。
   > * 在更高的层面webpack的配置中loader有两个目标：
   > * + `test` 属性，用于标识出应该被对应的 loader 进行转换的某个或某些文件。
   >   + `use` 属性，表示进行转换时，应该使用哪个 loader。

   ```
   const path = require('path');
   
   const config = {
     output: {
       filename: 'my-first-webpack.bundle.js'
     },
     module: {
       rules: [
         { test: /\.txt$/, use: 'raw-loader' }
       ]
     }
   };
   
   module.exports = config;
   ```

   

4. 插件（plugins）

> loader 被用于转换某些类型的模块，而插件则可以用于执行范围更广的任务。插件的范围包括，从打包优化和压缩，一直到重新定义环境中的变量，插件接口功能及其强大，可以用来处理各种各样的任务
>
> + 使用插件的话需要：require()它，然后把它添加到`plugins` 数组中。多数插件可以通过选项（option）自定义。也可以在配置文件中因为不同目的而多次使用同一个插件，这时需要通过使用new操作符创建一个实例
> + 在webpack.config.js中配置

> ```
> const HtmlWebpackPlugin = require('html-webpack-plugin'); // 通过 npm 安装
> const webpack = require('webpack'); // 用于访问内置插件
> 
> const config = {
>   module: {
>     rules: [
>       { test: /\.txt$/, use: 'raw-loader' }
>     ]
>   },
>   plugins: [
>     new HtmlWebpackPlugin({template: './src/index.html'})
>   ]
> };
> 
> module.exports = config;
> ```

5. 模式

> 通过选择`development` 或者`production` 之中的一个，来设置`mode` 参数，你可以启用相应模式下的webpack内置的优化
>
> ```
> module.exports = {
>   mode: 'production'
> };
> ```