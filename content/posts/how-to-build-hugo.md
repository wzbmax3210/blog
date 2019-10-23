---
title: "使用Hugo搭建个人博客"
date: 2019-10-23T14:20:26+08:00
draft: true
---
1.从[Hugo](https://gohugo.io/)官网的[Install](https://github.com/gohugoio/hugo/releases)页面下载相应系统的安装文件

> 因为自己是windows7，所以使用[hugo_0.57.2_Windows-64bit.zip](https://github.com/gohugoio/hugo/releases/download/v0.57.2/hugo_0.57.2_Windows-64bit.zip)解压后得到exe文件
然后将exe文件所在的目录加入环境变量

2.验证是否安装成功

>在命令行中执行`hugo version`，安装成功会输出版本信息  
>我的是Hugo Static Site Generator v0.57.2-A849CB2D windows/amd64 BuildDate: 2019-08-17T17:54:13Z

3.创建站点

>输入`hugo new site myblog`就会得到一个myblog的目录

4.添加文章

>进入myblog目录，输入`hugo new posts/first-post.md`就会在`content/posts`下生成`first-post.md`文件，  就可以在这里面使用md语法写blog。  
>记得在最终要发布的时候将`draft:true`改成false，draft是草稿的意思

5.预览文章

>输入`hugo server -D`，然后根据提示打开[http://localhost:1313/](http://localhost:1313/)就可以看到文章效果

6.生成静态页面

>输入`hugo`就会在public目录下生成静态页面文件
>此时可以将public单独设置一个仓库关联github然后就可以将博客上传到github page