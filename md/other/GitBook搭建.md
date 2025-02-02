# GitBook搭建

## 环境准备

### 1.安装Nodejs(10.24.1)

官网下载安装包安装，安装完成后使用以下命令查看

```bash
# 查看node的版本
node -v
# 查看npm的版本
np
```



### 2.安装GitBook

```bash
npm install -g gitbook-cli
```



### 3.初始化项目

**3.1.GitBook初始化**

创建一个文件夹，进入文件夹中，执行下面命令，初始化gitbook项目

```bash
gitbook init
```

创建成功信息

```
info: create README.md
info: create SUMMARY.md
```



**3.2.npm初始化**

执行下面命令，初始化为npm项目

```bash
npm init
```

运行成功后会生成一个文件 package.json，这个就是node的项目文件



### 4.项目启动

**4.1使用gitbook命令**

```bash
gitbook serve
```



**4.2.配置 package.json 里面的 js 脚本命令**

```c++
{
  "name": "gitbook",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "serve": "gitbook serve",  // 运行命令
    "build": "gitbook build"   // 打包命令
  },
  "author": "",
  "license": "ISC"
}
```

运行成功后会生成一个 _book 文件夹，这个目录就是我们的静态文件输出命令



## 章节配置

本质上使用的**MarkDown**语法，在**SUMMARY.md**文件中添加如下内容就可以添加章节和子章节

```markdown
# Summary

* [Introduction](README.md)

- [1](1.md) # 章节
  - [1.1](1.1.md) # 子章节
- [2](1.md)
  - [2.1](1.1.md)

```



## 忽略文件

任何在文件夹中的文件，在最后生成电子书时都会被拷贝到输出目录中，如果想要忽略某些文件，和Git一样，GitBook 会依次读取 .gitignore, .bookignore, .ignore 文件来将一些文件和目录排除。



## 插件使用

**1.创建book.js文件**

```javascript
module.exports = {
    "title" : "lhz的编程笔记",
    "author" : "lhz",
    "lang" : "zh-cn",
    // 插件列表
    "plugins": [],
    // 插件全局配置
    "pluginsConfig": {},
    // 模板变量
    variables: {},
}
```



**2.搜索强化插件**

强化搜索，使其支持各种字符集以及中文，支持高亮

https://www.npmjs.com/package/gitbook-plugin-search-pro

```bash
# 安装插件
npm install gitbook-plugin-search-pro
```



**3.代码框插件**

显示行号，有代码框复制按钮

https://www.npmjs.com/package/gitbook-plugin-code

```c++
# 安装插件
npm install gitbook-plugin-code
```



**4.自定义主题插件**

安装主题：gitbook-plugin-theme-主题名

```c++
# 安装插件
npm install gitbook-plugin-theme-主题名
```



**5.菜单折叠插件**

只显示父级菜单，子集菜单折叠

```bash
# 安装插件
npm install gitbook-plugin-expandable-chapters
```



**6.返回顶部插件**

返回页面顶部

```bash
# 安装插件
npm install gitbook-plugin-back-to-top-button
```



## 使用github Page部署在github上

可以自行查找部署