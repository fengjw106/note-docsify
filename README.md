1. # noteDocsify

   #### 介绍

   用于展示学习笔记的docsify服务

   #### 软件架构

   A magical documentation generator.

   #### 安装教程

   - 电脑已安装npm包管理工具

     全局安装docsify脚手架`npm i docsify-cli -g`，注意是安装脚手架docsify-cli，不是安装docsify！

   * 初始化项目文件夹docs

     `docsify init docs`

   * 本地预览

     `docsify serve docs`，浏览器打开localhost:3000页面即可看到。

   * 全局命令启动本地预览（可选）

     * `npm init -y`初始化一个package.json文件
     * 打开并在scripts中写入`"doc": "docsify serve docs"`
     * 之后就可以使用全局命令`npm run doc`启动本地预览。

   #### 参考文档

   - [docsify官方中文文档](https://docsify.js.org/#/zh-cn/quickstart)
   - 官方文档很浅显，还需要详细解惑，两篇文章可以引用一下，[第一篇](https://segmentfault.com/a/1190000017576714)，[第二篇](https://mp.weixin.qq.com/s?__biz=Mzg2OTA0Njk0OA==&mid=2247486555&idx=2&sn=8486026ee9f9ba645ff0363df6036184&chksm=cea24390f9d5ca86ff4177c0aca5e719de17dc89e918212513ee661dd56f17ca8269f4a6e303&token=298703358&lang=zh_CN#rd) 
