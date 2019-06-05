
[TOC]

## GitBook book.json 说明及使用

|Question|Answer|
|:--|:--|
|`book.json`是用来做什么的?|配置 `Gitbook` 生成静态页面的配置文件|
|`book.json`怎么创建放在那里？|手动创建，`gitbook` 项目的根目录，和 [SUMMARY.md](../SUMMARY.md) 同级|
|`book.json`有哪些配置？|`title`, `author`, `description`, `language`, `links` , `styles`, `plugins`, `pluginsConfig` </br> [字段说明](#attribute)</br> [本项目book.json配置](#book_json)|
|styles中的样式指定文件`( "website": "assert/style/website.css",)`怎么生成？|自己创建和编写，根据需求调整样式，路径可以自己定义，</br> [详细配置](#styles)|
|在book.json配置plugins 后怎么生效呢？| 1. 首先插件要配置正确，名称千万不要错，</br> 2. 安装插件，[这里介绍三种方法](#plugin_install) </br> 3. gitbook buil 即可生效|
|默认插件有哪些？屏蔽默认插件如何操作|1. 屏蔽默认插件，在 `book.json` 中 的 `plugins` 中配置 `-highlight` 这样就去掉了默认的高亮插件， </br>2. [默认的插件有](#default_plugins)|
|常见的插件有哪些？|[常见的插件说明及使用](#some_plugins)|


## book.json 字段说明
<div id="attribute">

|属性|含义|Demo|
|:--|:--|:--|
|title|设置书本的标题|"title": "Knowledge"|
|author|作者的相关信息|"author": "Royal"|
|description|本书的简单描述|"description":"这是我的环境配置说明"|
|language|Gitbook使用的语言| "language": "zh-hans"|
|styles|自定义页面样式，用于 book build|"style":{ "website": "assert/style/website.css"}|
|plugins|插件列表|"plugins":{"back-to-top-button"}|
|pluginsConfig| 插件配置 | 具体配置根据使用的插件进行配置 |
</div>

## styles 的配置
> 目前style配置根据导出的文件类型来，目前也就下面几种类型

<div id="styles">

|styles Key|含义|
|:--|:--|
|website|生成Html将会使用的样式文件|
|ebook|生成ebook.....|
|pdf|生成pdf.....|
|mobi|生成mobi.....|
|epub|生成epub.....|

</div>

## gitbok 插件安装的方法
<div id="plugin_install">

1. 在根目录下执行 `gitbook install` 
2. 使用npm安装，命令格式 `npm install gitbook-plugin-插件名字`，如 `npm install gitbook-plugin-code`
3. 从 `GitHub` 下载源码，放到`node_modules`文件夹里
</div>

## gitbook 默认插件

<div id="default_plugins">

|插件名词|说明|
|:--|:--|
|highlight：|代码高亮|
|search：|导航栏查询功能（不支持中文）|
|sharing：|右上角分享功能|
|font-settings：|字体设置（最上方的"A"符号）|
|livereload：|为GitBook实时重新加载|

</div>

## book.json 实例
<div id="book_json">

```json
{
    "title": "Knowledge",
    "language": "zh-hans",
    "plugins": [
        "code",
        "back-to-top-button",
        "tbfed-pagefooter",
        "search-pro",
        "fontsettings",
        "simple-page-toc",
        "links"
    ],
    "styles": {
        "website": "assert/style/website.css",
        "ebook": "assert/style/ebook.css",
        "pdf": "assert/style/pdf.css",
        "mobi": "assert/style/mobi.css",
        "epub": "assert/style/epub.css"
    },
    "pluginsConfig": {
        "tbfed-pagefooter": {
            "copyright": "pengqinping",
            "modify_label": "最后更新时间：",
            "modify_format": "YYYY-MM-DD HH:mm:ss"
        }, 
        "fontsettings": {
            "theme": "white",
            "family": "serif",
            "size": 12
        },
        "simple-page-toc": {
            "maxDepth": 3,
            "skipFirstH1": true
        },  
        "links": {
            "gitbook": false
        }
    }
}
```
</div>