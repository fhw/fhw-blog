## 静态资源处理

你会注意到在项目结构中有两个静态资源目录：`src/assets` 和 `static/` 。这两个目录有什么区别？
## webpack的Assets
要弄清楚这个问题，我们首先要理解webpack是怎么处理静态资源的。在`*.vue`组件中，所有template和CSS通过`vue-html-loader`和`css-loader`编译后来查找静态资源路径。例如，在`<img src="./logo.png">`和`background: url(./logo.png)`中, `"./logo.png"`使用的是相对路径，并且将被webpack当做一个依赖模块处理。

因为`logo.png`不是JavaScript，当它作为一个依赖模块的时候，我们需要`url-loader`和`file-loader`来处理它。这个webpack模板已经为你配置好这些loaders，所以你获得像`filename fingerprinting(缓存清除技术)`和内联base64等功能，使用相对/模块路径时就不必担心部署。

由于这些静态资源可能在构建过程中被内联/复制/重命名，因此它们基本上是源代码的一部分。这就是为什么建议将Webpack处理的静态资源放置`/src`在其他源文件中的原因。实际上，你甚至不需要全部放入`/src/assets`：你可以根据使用它们的模块/组件来组织它们。例如，您可以将每个组件放在其自己的目录中，其静态资产就位于其旁边。
    
