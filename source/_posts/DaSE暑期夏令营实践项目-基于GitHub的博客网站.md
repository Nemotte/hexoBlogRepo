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

![](https://www.nemotte.cn/wordpress/wp-content/uploads/2023/07/QQ截图20230704103438.png)

#### 文章

![](https://www.nemotte.cn/wordpress/wp-content/uploads/2023/07/QQ截图20230704103438-1.png)

#### 小游戏

![](https://www.nemotte.cn/wordpress/wp-content/uploads/2023/07/QQ截图20230704103438-2.png)



## 
