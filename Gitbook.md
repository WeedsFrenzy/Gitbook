# GitBook

## What is Gitbook

Gitbook是一个开源免费的软件，它是一个基于Node.js的命令行工具，作用是帮助我们使用Markdown语法来编排书籍，同时也支持HTML语法。

- 官方地址：https://github.com/GitbookIO/gitbook
- 书籍备份上传
  - 官方网站：https://www.gitbook.com/
  - 国内推荐使用：Github、Coding、Gitee等

## How to install GitBook

- 安装NVM版本Node.js控制工具：https://github.com/coreybutler/nvm-windows

- ```
  nvm install 10.22.0 （高版本的node.js可能不适配）
  nvm use 10.22.0
  
  Tips:使用 nvm install 命令下载新的Node版本会比较慢，这时可以直接从网址：https://nodejs.org/zh-cn/download/releases/上下载所需版本，并安装到nvm的源文件夹下
  ```

- 更新npm国内源

- ```
  npm config set registry=http://registry.npm.taobao.org -g
  ```

- 通过npm安装Gitbook

- ```
  npm install -g gitbook-cli
  ```

## How to use Gitbook

### 基本使用

1、初始化书籍目录

```
gitbook init
```

- 执行该命令后，在文件夹下会生成以下两个文件

```
README.md  -- 书籍的简单介绍
SUMMARY.md -- 书籍的目录结构
```

2、编译和预览书籍

```
gitbook serve
```

- 首先会调用gitbook build编译书籍并在当前目录下生成_book文件夹，里面存放md转html的文件，之后会启动web服务器，监听端口是4000。

### 编写书籍内容

以README.md文件为例，与Git一致，该文件是本书籍项目的介绍文件。

```
详见README.md文件
```

- Markdown语法
- HTML语法

### 编写书籍目录

- 修改SUMMARY.md文件
- Gitbook以无序列表形式组织目录

```
# Summary

* [Introduction](README.md)
* [前言](readme.md)
* [第一章](part1/README.md)
    * [第一节](part1/1.md)
    * [第二节](part1/2.md)
    * [第三节](part1/3.md)
    * [第四节](part1/4.md)
* [第二章](part2/README.md)
* [第三章](part3/README.md)
* [第四章](part4/README.md)
```

- [] -- 章节名
- () -- 章节路径

### 修改Gitbook配置

Gitbook的配置文件为book.json，如果没有则新建

```
{
	// 最上面浏览器导航栏的名称
    "title" : "Gibook Use",   
    // 书籍简要描述
    "description" : "记录Gitbook的配置和一些插件的使用",
    // 书籍作者
    "author" : "zhangjikai",
	// 使用的语言
    "language" : "zh-hans",
    // 指定版本
    // "gitbook" : "2.6.4",
    // 侧边栏添加链接
    "links" : {
        "sidebar" : {
            "Home" : "http://zhangjikai.com",
            "百度" : "https://baidu.com"
        }
    },
    // 样式设置（默认如下 ）
    "styles": {
    	"website": "styles/website.css",
    	"ebook": "styles/ebook.css",
    	"pdf": "styles/pdf.css",
    	"mobi": "styles/mobi.css",
    	"epub": "styles/epub.css"
	}
    // 使用的插件
   "plugins": [
        "disqus",
        "-search",
        "search-pro@1.0.7",
        "advanced-emoji@0.1.5",
        "github",
        "ace",
        "emphasize",
        "katex",
        "anchors",
        "include-codeblock",
        "mermaid",
        "tbfed-pagefooter",
        "sectionx",
        "expandable-chapters",
        "codeblock-filename",
        "baidu",
        "sitemap@1.0.2",
        "donate",
        "local-video",
        "toc",
        "edit-link"

    ],
    // 插件对应的配置信息
    "pluginsConfig": {
        "disqus": {
            "shortName": "gitbookuse"
        },
        "github": {
            "url": "https://github.com/zhangjikai/gitbook-use"
        },
        "search-pro": {
            "cutWordLib": "nodejieba",
            "defineWord": ["gitbook-use"]
         },

        "sharing": {
            "weibo": true,
            "facebook": true,
            "twitter": true,
            "google": false,
            "instapaper": false,
             "vk": false,
            "all": [
                "facebook", "google", "twitter",
                "weibo", "instapaper"
            ]
        },

        "tbfed-pagefooter": {
            "copyright":"Copyright &copy zhangjikai.com 2015",
            "modify_label": "该文件修订时间：",
            "modify_format": "YYYY-MM-DD HH:mm:ss"
        },

        "baidu": {
            "token" : "ff100361cdce95dd4c8fb96b4009f7bc"
        },
        "sitemap": {
            "hostname": "http://gitbook.zhangjikai.com"
        },

        "donate": {
          "wechat": "http://zhangjikai.com/resource/weixin.png",
          "alipay": "http://zhangjikai.com/resource/alipay.png",
          "title": "",
          "button": "赏",
          "alipayText": "支付宝打赏",
          "wechatText": "微信打赏"
        },

         "edit-link": {
                "base": "https://github.com/zhangjikai/gitbook-use/edit/master",
                "label": "Edit This Page"
         }

    }
}
```

#### 个人通用配置

```
{
    "title": "Gitbook使用指南",
    "description": "Gitbook电子书教程",
    "author": "WeedsFrenzy",
    "language": "zh-hans",
    "root": ".",
    "plugins": [
        "donate",
        "github",
        "edit-link",
        "back-to-top-button",
        "code",
        "insert-logo",
        "-lunr",
        "-search",
        "search-pro",
        "advanced-emoji",
        "splitter",
        "-sharing",
        "sharing-plus",
        "tbfed-pagefooter",
        "page-toc-button",
        "popup",
        "expandable-chapters-small",
        "todo"
    ],
    "pluginsConfig": {
        "donate": {
            "wechat": "/assets/images/wechatpay.jpg",
            "alipay": "/assets/images/alipay.jpg",
            "title": "",
            "button": "打赏",
            "alipayText": "支付宝打赏",
            "wechatText": "微信打赏"
        },
        "github": {
            "url": "https://github.com/GitbookIO/gitbook"
        },
        "edit-link": {
            "base": "https://github.com/GitbookIO/gitbook/blob/master/README.md",
            "label": "Edit This Page"
        },
        "insert-logo": {
            "url": "/assets/images/logo.png",
            "style": "background: none; width: 150px; height: 150px;"
        },
        "sharing": {
            "douban": false,
            "facebook": false,
            "google": false,
            "pocket": false,
            "qq": false,
            "qzone": false,
            "twitter": false,
            "weibo": false,
            "all": [
                "douban",
                "facebook",
                "google",
                "instapaper",
                "linkedin",
                "twitter",
                "weibo",
                "messenger",
                "qq",
                "qzone",
                "viber",
                "whatsapp"
            ]
        },
        "tbfed-pagefooter": {
            "copyright": "Copyright &copy xxxx.com 2021",
            "modify_label": "该文件修订时间：",
            "modify_format": "YYYY-MM-DD HH:mm:ss"
        }
    }
}
```

## Gitbook插件

### 插件查找与使用

#### 查找插件

- 在[npm官网](https://www.npmjs.com/)搜索插件，如：[gitbook-plugin-summary](https://www.npmjs.com/package/gitbook-plugin-summary)
- https://www.npmjs.com/search?q=keywords:gitbook

#### 使用插件

- 插件详情页有关于插件的使用说明

  - 安装插件

  - ```
  1、直接npm安装（推荐）
    npm i gitbook-plugin-summary --save
  2、最后在统一执行gitbook install命令（速度会比较慢）
    ```
  
  - 使用插件（在book.json的plugins字段内添加插件名称，如果有需要还需要添加对应插件的配置）
  
  - ```
    {
      "plugins": [
        "summary"
      ]
    }
    ```
  
  - 启动服务
  
  - ```
    gitbook serve
    ```

### 常用插件

Gitbook默认自带有5个插件：

- highlight： 代码高亮
- search： 导航栏查询功能（不支持中文）
- sharing：右上角分享功能
- font-settings：字体设置（最上方的"A"符号）
- livereload：为GitBook实时重新加载

```
在配置插件时，如果前面加上-，则表示去除默认插件
```

#### 打赏按钮

- gitbook-plugin-donate(打赏按钮): https://www.npmjs.com/package/gitbook-plugin-donate

#### GitHub按钮

- gitbook-plugin-github(GitHub按钮): https://www.npmjs.com/package/gitbook-plugin-github

#### GitHub编辑按钮

- gitbook-plugin-edit-link(GitHub编辑按钮): https://www.npmjs.com/package/gitbook-plugin-edit-link

#### 回到顶部

- gitbook-plugin-back-to-top-button：https://www.npmjs.com/package/gitbook-plugin-back-to-top-button

#### 导航目录折叠

- gitbook-plugin-expandable-chapters-small：https://www.npmjs.com/package/gitbook-plugin-expandable-chapters-small

#### 代码赋值&行号

- gitbook-plugin-code：https://www.npmjs.com/package/gitbook-plugin-code

#### TODO功能

- gitbook-plugin-todo：https://www.npmjs.com/package/gitbook-plugin-todo

#### LOGO

- npm i gitbook-plugin-insert-logo：https://www.npmjs.com/package/gitbook-plugin-insert-logo

#### 中文搜索

- gitbook-plugin-search-pro：https://www.npmjs.com/package/gitbook-plugin-search-pro

#### 支持emoji表情

- 表情列表：https://www.webfx.com/tools/emoji-cheat-sheet/
- gitbook-plugin-advanced-emoji：https://www.npmjs.com/package/gitbook-plugin-advanced-emoji

#### 侧边栏可调节

- gitbook-plugin-splitter：https://www.npmjs.com/package/gitbook-plugin-splitter

#### 分享扩展

- gitbook-plugin-sharing-plus：https://www.npmjs.com/package/gitbook-plugin-sharing-plus

#### 页脚版权信息

- gitbook-plugin-tbfed-pagefooter：https://www.npmjs.com/package/gitbook-plugin-tbfed-pagefooter

#### 生成业内目录

- gitbook-plugin-page-treeview：https://www.npmjs.com/package/gitbook-plugin-page-treeview

#### 悬浮目录

- gitbook-plugin-page-toc-button：https://www.npmjs.com/package/gitbook-plugin-page-toc-button

#### 阅读量计数

- gitbook-plugin-pageview-count：https://www.npmjs.com/package/gitbook-plugin-pageview-count

#### 弹出大图

- gitbook-plugin-popup：https://www.npmjs.com/package/gitbook-plugin-popup

#### 评论功能

- gitbook-plugin-mygitalk：https://www.npmjs.com/package/gitbook-plugin-mygitalk

## Gitbook部署

### Github

- 私有库的GitPage需要收费，公有的是免费的

- 下载安装Git：https://git-scm.com/downloads

- 在Github上新建仓库（Gitbook）

- 在本地的Gitbook文件夹下执行`git init`命令，初始化git

- 执行如下命令，更新整个项目

- ```
  git add .
  git commit -m "docs 添加源码"
  ```

- 建立与远程仓库的关联并上传代码

- ```
  git remote add origin git@github.com:WeedsFrenzy/Gitbook.git
  git branch -M main
  git push -u origin main
  ```

- 新建gh-pages分支用于保存编译后的HTML文件

- ```
  复制main分支下的_book文件夹内容
  创建并切换到gh-pages分支：git checkout -b gh-pages
  将除.git文件夹外的所有文件删除
  将_book文件夹内的内容复制到当前分支下的文件夹
  提交更新：
  	git add .
      git commit -m "docs 添加HTML"
  上传到远程仓库：git push origin gh-pages
  ```

- 点击远程仓库的settings并选择Pages

- Github Pages会使用项目下的index.html文件夹作为初始页面文件

- 点击即可访问该项目

## 常见问题

### 图片显示问题

- 上传到Github后，文件读取的路径与本地并不一致
- 目前已知两种解决方法

```
1、将图片上传至图床，使用外部链接
2、将图片路径改为Github上可以访问到的绝对路径（相当于图床）
要点到下载按钮，正确的图片路径如下所示：
https://raw.githubusercontent.com/WeedsFrenzy/Gitbook/gh-pages/assets/images/logo.PNG
```

## 参考资料

- Gitbook安装使用避坑：https://blog.csdn.net/qq_43528771/article/details/107949010
- Gitbook学习使用笔记：https://zq99299.gitbooks.io/gitbook-guide/content/
- Gitbook插件整理：https://www.jianshu.com/p/427b8bb066e6
- Gitbook电子书教程：https://sphard.com/ebooks/gitbook/
