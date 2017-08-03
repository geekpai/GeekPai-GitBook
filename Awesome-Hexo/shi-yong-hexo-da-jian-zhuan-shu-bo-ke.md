# 使用GitHub Pages+Hexo搭建博客

## 1.环境环境

### 1.1 安装Git

> [下载地址：https://git-scm.com/downloads][1]

### 1.2 安装Node.js
> [下载地址：http://nodejs.org/download/][2]

## 2.配置Github

### 2.1 建立Github Repository
> 访问：[Github官网][3]，新建一个与你用户名一致的仓库，仓库名必须为：your_user_name（Github账号名）.github.io

### 2.2 配置SSH-Key

## 3.快速上手Hexo

### 3.1安装
> 打开Git命令行，执行如下命令：`npm install -g hexo`

### 3.2开始创建
> 在电脑中建立一个名字叫Hexo的文件夹，然后在此文件夹中执行命令：`hexo init`Hexo随后会自动在目标文件夹建立网站所需要的文件。
> 然后按照提示，执行命令: `npm install`在该目录下安装node_modules的相关文件

### 3.3开启服务
> 执行命令：`hexo server`开启服务，提示Hexo is running at http://localhost:4000/. Ctrl+C to stop.
> 表明Hexo Server已经启动了，在浏览器中打开`http://localhost:4000/`，Hexo已经生成了一篇文章。

### 3.4创建文章
> 打开一个新的git bash命令行窗口，进到Hexo下，执行命令：`hexo new "pageName"`刷新`http://localhost:4000/`，即可生成新的文章“pageName”。

### 3.5生成静态网页
> 执行命令：`hexo generate`即可将markdown文件生成静态网页

### 3.6编辑文章
> 对于生成的文件可以使用支持MarkDown的编辑工具进行编辑

### 3.7部署到Github
> 部署到Github前需要配置_config.yml文件，首先找到下面的内容

### 3.8测试网页
> 当部署完成后，在浏览器中打开http://youusername.github.io/，网页正常显示，则表明部署已经成功。、

## 4.常用命令

> hexo new "postName" #新建文章
> hexo new page "pageName" #新建页面
> hexo generate #生成静态页面至public目录
> hexo server #开启预览访问端口（默认端口4000，'ctrl + c'关闭server）
> hexo deploy #将.deploy目录部署到GitHub
> hexo help  # 查看帮助
> hexo version  #查看Hexo的版本
> hexo deploy -g  #生成加部署
> hexo server -g  #生成加预览
> >简化命令：
> >hexo n == hexo new
> >hexo g == hexo generate
> >hexo s == hexo server
> >hexo d == hexo deploy

[1]: https://git-scm.com/downloads
[2]: http://nodejs.org/download/
[3]: http://www.GitHub.com/