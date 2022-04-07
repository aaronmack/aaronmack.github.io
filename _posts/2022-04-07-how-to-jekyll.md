---
layout: post
title: My first blog - how to use Jekyll
date: 2022-04-07 19:39:00
comments: true
tags: jekyll 
categories: tech
description: An example of how to use Jekyll to generate personal home page
---

[Jekyll](https://jekyllrb.com/)可以帮助我们将***.md** (Markdown)文件生成静态的网页来浏览。首先来看一下静态与动态的区别

<center>

{% graphviz %}
digraph {
  node [shape=circle, style=filled];
  Markdown [fillcolor=green];
  Html [fillcolor=yellow];
  GithubPages [fillcolor=purple];
  Markdown -> Html [label=Static];
  Html -> GithubPages [];
  Markdown -> GithubPages [label=Dynamic];
}
{% endgraphviz %}

</center>

如图中所示，如果是静态部署到GithubPages上去，需要先将我们的Markdown文件转成Html，再进行部署，如果是动态部署我们省略转成Html这一步；关于动态部署，参考[Docsify](https://docsify.js.org/)，以及这里有我之前搭建的一个[Docsify Template](https://github.com/AAaronMack/aaaronmack.github.io),还有最终的一个[效果](https://aaaronmack.github.io/#/)，其存储的大部分都是Markdown，而没有Html文件。但这也没有关系，Jekyll可以自动生成Html，总之静态与动态这两者各有优缺点。

---

## Before You Begin

1. [Scoop](https://scoop.sh/) - 一个Windows下的命令行安装程序，包含了我们日常生活中大部分的使用软件

2. [msys2](https://www.msys2.org/) - 一组Windows下的工具和库

    ```bash
    # 如果你已经安装了scoop，则只需要简单的执行
    scoop install msys2
    ```

3. [Ruby](https://www.ruby-lang.org/en/) - 一种动态编程语言

    ```bash
    # 如果你已经安装了scoop，则只需要简单的执行
    scoop install ruby
    ```

> <span style="color:red;font-weight:bold">Note</span>
> 
> 1. 在安装成功`msys2`后首先执行一次
> 2. 在完成上述三步后，还需要执行`ridk install`,如下图中所示的<mark>结果</mark>
> <div align=center><img src="https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/tech/jekyll-ridk-install.50u9c0il7o80.webp"></div>

---

## General steps

1. 安装jekyll和bundler - bundler可以在某种程度上将其理解为为python的pip，包管理工具

    ```bash
    gem install jekyll bundler
    ```

2. 创建一个新的Jekyll网页，例如这里名称叫做`myblog`

    ```bash
    jekyll new myblog
    ```

3. 在本地部署以及预览它的效果

    ```bash
    bundle exec jekyll serve --livereload
    ```

> Note
> 
> 1. `--livereload`命令行参数可以看到实时更改Markdown文件的效果，但对于`_config.yml`等一些文件则需要重新执行命令

### Advanced steps

在General steps中我们已经可以生成一个简单的网页，但如果想要更进一步，我们可以这样做

1. 访问https://github.com/alshedivat/al-folio，将这个仓库Fork到我们的Github上 (这里是选择了一个Jekyll的主题，当然你也可以选择你喜欢的任何主题)


2. 重命名这个仓库名称为`<your-github-username>.github.io`


3. 设置Github，有步骤 `Settings -> Pages -> Source`选择*gh-pages*,点击*Save*即可

根据自己的需要修改这个仓库中的文件，例如添加我们自己的的Blog，设置我们的个人主页等等;这个仓库已经配置好了诸如自动部署，自动构建等等所需要的步骤，这样每当我们有新的**Commit**提交的时候，都会自动进行的

---

## Solve

**Error 1** - in require: cannot load such file -- rake (LoadError...

 * 这个是关于[rake](https://github.com/ruby/rake)的错误，遇见这个错误时，可以通过尝试重新安装ruby解决，如果使用scoop的话，可以执行`scoop uninstall ruby`再执行`scoop install ruby`

<br>

**Error 2** - github-pages build Failure 
<div align=center><img src="https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/tech/jekyll-githubpages-build-faiure.1r87idn3bzfk.webp"></div>

 * 如图中那样，在部署到Github-pages后，遇到build(构建)错误,我这里使用的是Jekyll的[al-folio](https://github.com/alshedivat/al-folio)这个主题,在`README.md`中提到，如果需要部署到Github-pages上时，需要将`_config.yml`中的`url`设置为我们的仓库地址，以及将`baseurl`留空。

---
<center>Please feel free to contact me if you have any questions.😊</center>

---
