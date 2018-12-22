## 简介
在公司一般都要进行项目管理，SVN或git。另外公司也会有一些公用组件与工具类等。
在 [快速开始](ionic/quickStart.md) 中，有些与公司开发流程一致。

## 目录结构
下载远程仓库的代码后，可以看到项目的目录结构：也就是两个文件，7个文件，看起来非常少。但已经包含项目中所需要管理的所有内容，你需要做可能只是处理下面pages文件夹，其他的东西你不需要提交也可能没有提交权限。

```
|--resources                  // 图标、启动页资源图片
|--src                        // 源代码
|----app                      // 入口文件
|----assets                   // 主题、字体等静态资源
|----components               // 全局公用组件
|----providers                // 全局服务
|----pages                    // 页面。
|----theme                    // 主题文件
|----index.html               // 主入口文件
|----module.ts                // 模块加载文件
|--.editorconfig              // 
|--config.xml                 // app配置文件
|--ionic.config.json          // 
|--ionic.starter.json         // 
|--package.json               // 以来管理文件
|--tsconfig.json              // ts 配置项
|--tslint.json                // tslint 配置项
```

## 开始开发
说了上边已经包含你开发前所需要的一切，那么缺少的部分当然就需要你去补全了，也就是属于开发者的开发部分的工作。
* 安装依赖。 `npm i` 或 `npm install`
* 预览。`ionic serve`



