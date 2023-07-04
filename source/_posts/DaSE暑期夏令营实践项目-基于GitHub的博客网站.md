---
title: DaSE暑期夏令营实践项目--基于GitHub的博客网站
date: 2023-07-04 01:02:15
categories: 
- 项目报告
---



# DaSE暑期夏令营实践项目--基于GitHub的博客网站

| 申请专业：大数据技术与工程 | 年级：2024        | 类别：专业型硕士 |
| -------------------------- | ----------------- | ---------------- |
| 教师：蒲鹏                 | 姓名：金子龙      | 日期：2023/07/04 |



## 项目内容

部署一个静态网页博客。静态网页博客是一种不需要后端服务器和数据库支持的网站，只需要使用 HTML、CSS 和 JavaScript 等前端技术就可以实现。静态网页博客有很多优点，比如速度快、安全稳定、易于维护等。

你需要选择一个自己感兴趣或擅长的主题来制作一个静态网页博客，比如个人介绍、爱好分享、技术总结等。你需要设计至少四个页面来展示博客内容，不限于首页、关于我、文章列表、文章详情等。



## 项目概览

### 环境信息

本项目使用Hexo框架+GitHub Pages，版本信息如下：

```
hexo: 6.3.0
hexo-cli: 4.3.1
os: win32 10.0.19045
node: 18.16.0
acorn: 8.8.2
ada: 1.0.4
ares: 1.19.0
brotli: 1.0.9
cldr: 42.0
icu: 72.1
llhttp: 6.0.10
modules: 108
napi: 8
nghttp2: 1.52.0
nghttp3: 0.7.0
ngtcp2: 0.8.1
openssl: 3.0.8+quic
simdutf: 3.2.2
tz: 2022g
undici: 5.21.0
unicode: 15.0
uv: 1.44.2
uvwasi: 0.0.15
v8: 10.2.154.26-node.26
zlib: 1.2.13
```



选用的Hexo主题为Zhl，依赖的插件为：

```sh
npm install 
"dependencies": {
    "hexo": "^3.2.0",
    "hexo-generator-archive": "^0.1.4",
    "hexo-generator-category": "^0.1.3",
    "hexo-generator-index": "^0.2.0",
    "hexo-generator-tag": "^0.2.0",
    "hexo-renderer-ejs": "^0.3.0",
    "hexo-renderer-stylus": "^0.3.1",
    "hexo-renderer-marked": "^0.3.0",
    "hexo-server": "^0.2.0"
  },
  "devDependencies": {
    "hexo-browsersync": "^0.3.0",
    "hexo-renderer-ejs": "^0.3.1",
    "hexo-renderer-stylus": "^0.3.3",
    "hexo-server": "^0.2.2"
  }
```



### 项目布局

```
├─node_modules
├─public
├─scaffolds
├─source							# 存放页面、文章
│  ├─about							# 关于页面
│  ├─categories						# 分类页面
│  ├─game							# 小游戏页面
│  ├─lab01							# 实验页面
│  ├─lab02
│  ├─tags							# 标签页面
│  └─_posts							# 文章
├─themes							# 主题
    └─zhl
└─_config.yml						# 全局配置
```



### 页面预览

#### 主页

<img src="https://www.nemotte.cn/wordpress/wp-content/uploads/2023/07/QQ截图20230704103438.png" alt="size" style="zoom:33%;" />

#### 文章

<img src="https://www.nemotte.cn/wordpress/wp-content/uploads/2023/07/QQ截图20230704103438-1.png" style="zoom:33%;" />

#### 小游戏

<img src="https://www.nemotte.cn/wordpress/wp-content/uploads/2023/07/QQ截图20230704103438-2.png" style="zoom:33%;" />



## 主题选取

选用的Hexo主题为Zhl，依赖Hexo对分类、归档、标签的自动生成插件。在文章头部添加对应的分类、标签后，可以自动生成对应的分类、标签页面，在左侧小工具处可以查看。

<img src="https://www.nemotte.cn/wordpress/wp-content/uploads/2023/07/QQ截图20230704103438-3.png" style="zoom:33%;" />



## 页面实现

### 文章Post

Hexo一般通过Markdown语法书写文章，通过在Markdown头部增加控制语句来设置文章页面属性。

```
---
title: 《数据库系统原理》笔记
date: 2023-07-04 00:57:35
categories: 
- 计科专业课笔记
---
```



### 页面Page

Page可以用Markdown和HTML两种方式实现，以下详解HTML的实现方式。



#### 纯HTML

用命令行打开博客根目录，输入指令：

```
$ hexo new page <pagename>
```

在`source`文件夹下会新建一个`<pagename>`文件夹，结构如下：

```
├─source							# 存放页面、文章
│  ├─<pagename>						# 页面
|  |  └─index.md
```

将`index.md`重命名为`index.html`，在此文件中书写HTML代码，部署后即可在对应页面浏览效果。



例如：

```html
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Tb</title>
    <style>
      .hi {
        color: red;
      }
    </style>
  </head>
  <body>
    <p class="hi">hello world!</p>
    <h1>一级标题</h1>
    <h2>二级标题</h2>
    <h3>三级标题</h3>
    <h4>四级标题</h4>
    <h5>五级标题</h5>
    <ul>
      <li>无序列表</li>
      <li>无序列表</li>
      <li>无序列表</li>
    </ul>
    <ol>
      <li>有序列表</li>
      <li>有序列表</li>
      <li>有序列表</li>
    </ol>
    <!-- 图片 -->
    <img
      width="200"
      src="https://www.nemotte.cn/wordpress/wp-content/uploads/2022/06/test.png"
      alt="logo"
    />
    <br />
    <!-- 超链接 -->
    <a href="https://www.nemotte.cn" target="_blank">Nemotte's Blog</a>
    <!-- 斜体 -->
    <p>normal text <em>italic text</em></p>
    <!-- 粗体 -->
    <p>normal text <strong>bold text</strong></p>
    <!-- 输入框 -->
    <input type="text" />
    <br />
    <input type="text" placeholder="请填写文本信息" />
    <br />
    <!-- 复选框 -->
    <label
      ><input
        type="checkbox"
        name="cbox"
        id="cbox1-pro"
        value="first_checkbox"
      />first_checkbox</label
    >
    <label
      ><input
        type="checkbox"
        name="cbox"
        id="cbox2-pro"
        value="second_checkbox"
      />second_checkbox</label
    >
    <br />
    <!-- 选择文件 -->
    <input type="file" />
    <!-- 单选框 -->
    <label><input type="radio" name="radio1" id="radio1" />first_radio</label>
    <label><input type="radio" name="radio1" id="radio2" />second_radio</label>
    <br />
    <!-- 控制范围 -->
    <input type="range" />
    <br />
    <!-- 多行文本编辑 -->
    <textarea name="text" rows="5" cols="40"></textarea>
    <!-- 提交 -->
    <input type="submit" />
  </body>
</html>

```

效果如下：

<img src="https://www.nemotte.cn/wordpress/wp-content/uploads/2023/07/QQ截图20230704103438-4.png" style="zoom:33%;" />



#### HTML+CSS+JS

既然了解了页面部署的方式，那么任意HTML项目均可静态部署至Hexo Pages。

以下为示例结构，当然可以在`<pagename>`下部署任意结构的HTML项目。

```
├─source							# 存放页面、文章
│  ├─<pagename>						# 页面
|  |  ├─index.html
|  |  ├─temp.css
|  |  ├─temp.js
```



<img src="https://www.nemotte.cn/wordpress/wp-content/uploads/2023/07/QQ截图20230704103438-2.png" style="zoom:33%;" />

<img src="https://www.nemotte.cn/wordpress/wp-content/uploads/2023/07/QQ截图20230704103438-5.png" style="zoom:33%;" />



## GitHub Action 自动化项目部署

### 自动化部署概述

对于Hexo框架，如果要将本地文件推送到远程Git Pages上，需要依次执行如下三条指令：

```sh
$ hexo clean
$ hexo g
$ hexo d
```

如需在其他设备上发布/更新博文，则同样需要安装Hexo支撑环境，以及对应的Hexo插件，非常不便。

那么，如果在远程机器上安装好Hexo环境，通过GitHub Action直接在远程主机上执行上述三条指令，就能免去安装环境这一步骤，只需配置Git就能发布/更新博文了。



### 配置步骤

#### 新建仓库

对于Hexo框架，需要将编译后的HTML项目推送到`<username>.github.io`仓库中。但是我们需要新建一个仓库来保存Hexo项目源代码。

新建仓库后，将本地博客项目文件夹关联到此仓库，在`.github`文件夹下新建`workflow/main.yml`文件，输入下述配置：

```yaml
# workflow name
name: Hexo Blog CI

# master branch on push, auto run
on: 
  push:
    branches:
      - main
      
jobs:
  build: 
    runs-on: ubuntu-latest 
        
    steps:
    # check it to your workflow can access it
    # from: https://github.com/actions/checkout
    - name: Checkout Repository main branch
      uses: actions/checkout@main 
      
    # from: https://github.com/actions/setup-node  
    - name: Setup Node.js 18.x 
      uses: actions/setup-node@main
      with:
        node-version: "18.x"
    
    - name: Setup Hexo Dependencies
      run: |
        npm install hexo-cli -g
        npm install
        npm install hexo hexo-generator-archive hexo-generator-category hexo-generator-index hexo-generator-tag hexo-renderer-ejs hexo-renderer-stylus hexo-renderer-marked hexo-server --save
    
    - name: Setup Deploy Private Key
      env:
        HEXO_DEPLOY_PRIVATE_KEY: ${{ secrets.HEXO_DEPLOY_PRIVATE_KEY }}
      run: |
        mkdir -p ~/.ssh/
        echo "$HEXO_DEPLOY_PRIVATE_KEY" > ~/.ssh/id_rsa 
        chmod 600 ~/.ssh/id_rsa
        ssh-keyscan github.com >> ~/.ssh/known_hosts
        
    - name: Setup Git Infomation
      run: | 
        git config --global user.name 'Nemotte' 
        git config --global user.email 'jinzilong312@163.com'

    - name: Deploy Hexo 
      run: |
        hexo clean
        hexo generate 
        hexo deploy

```

这个配置的意义是，当源代码仓库接到本地的`push`指令后，自动执行`run`后面的指令。这一过程配置了远程主机的Hexo环境和依赖，并将Hexo项目推送到`<username>.github.io`的pages中。

**需要在源代码仓库中配置私钥和公钥，否则会推送失败。**



至此，我们在更新本地Hexo项目后，只需完成git push后，Git Pages会在Action执行后自动更新。



## 反思

我在本科期间一直有写博客的习惯。在大一的时候，自己租用了云服务器搭建Wordpress博客，并长时间使用，其中包括了各种项目和笔记。但是Wordpress博客的配置相对简单，而且操作基于图形化界面，几乎无门槛。当然，如果要完成站点的维护、页面的重排还是有门槛的，只是使用并无门槛。

<img src="https://www.nemotte.cn/wordpress/wp-content/uploads/2023/07/QQ截图20230704103438-6.png" style="zoom:33%;" />

而Hexo框架，相当于提供了主题配置+Markdown文章到HTML项目的编译功能，使用者对于项目的每一个细节都有更好的理解，可以更加简单地自定义设计和功能。并且Hexo搭建的是静态站点，加载速度明显高于Wordpress。



初学Hexo时，也碰到了很多问题，如**推送至远程Page后丢失CSS格式**，在全局配置中加入一行：

```yaml
root: /
```

即可解决。

如配置GitHub Action时，**远程Deploy失败**，根据报错在全局配置中修改HTML URL为SSH URL即可：

```diff
deploy:
  type: git
- repo: https://github.com/...
+ repo: git@github.com:...
  branch: main
```



## 链接

[DaSE静态博客](https://nemotte.github.io/)

[Nemotte的博客](https://www.nemotte.cn/)

