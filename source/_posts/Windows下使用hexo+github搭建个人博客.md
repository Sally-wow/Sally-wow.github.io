---
title: Windows下使用hexo+github搭建个人博客
date: 2021-10-17 17:30:02
categories: 学习笔记
---

## 1. 环境搭建

### 01、安装 Node.js

- 官网下载安装

  https://nodejs.org

- 命令行查看安装版本

  `node -v`       

- 安装cnpm包管理工具提高下载速度

  `npm install -g cnpm --registry=https://registry.npm.taobao.org`

### 02、安装hexo

- 命令行下安装

  `cnpm install -g hexo-cli`

- 验证是否安装成功
  `hexo -v`

### 03、安装 Git

- 官网下载安装

  https://git-scm.com/downloads

  在命令行输入：

  `git config --global user.name "用户名"`

  `git config --global user.email "邮箱"`

## 2. 部署博客

### 01、本地部署

- 创建博客文件夹

  在要放置博客文件的路径下，初始化一个博客：`hexo init blog`，并命名为blog，此时当前路径下会生成一个blog文件夹。

- 生成博客

  编写Markdown格式的文本，放在`blog\source\_posts`路径下

  让hexo框架自动渲染生成博客：`hexo g`

- 在本地服务器上运行博客：`hexo s` 

  `ctrl+c`退出

  部署成功后，可以在本机浏览器输入`localhost:4000`，预览效果

  可以在执行时使用 `-p` 选项指定其他端口，如下：

  ```
  hexo server -p 5000
  ```

### 02、远程部署在GitHub上

- 安装git部署工具

  `cnpm install hexo-deployer-git --save`

- 创建GitHub仓库

  登录github，新建仓库，仓库名称必须是`GitHub用户名.github.io`，与用户名不一致将导致部署失败。

- 设置配置文件`_config.yml`

  用记事本打开blog目录下的`_config.yml`文件，将deploy下的内容设置为如下内容：

  ```yaml
  # Deployment
  ## Docs: https://hexo.io/docs/one-command-deployment
  deploy:
    type: git
    repo: https://github.com/Sally-wow/Sally-wow.github.io.git
    branch: master
  ```

  仓库地址`repo：`设置为自己仓库的地址

  注意：所有冒号后都有一个空格

- 部署到github

  `hexo g`

  部署成功后可以访问https://sally-wow.github.io/



## 更新博客

将写好的内容放在`blog\source\_posts`路径下

1. 清除缓存文件 (`db.json`) 和已生成的静态文件 (`public`)。

   ```
   hexo clean
   ```

2. 生成网站静态文件到默认设置的 public 文件夹。

   - 便于查看网站生成的静态文件或者手动部署网站；
   - 如果使用自动部署，不需要先执行该命令；

   ```
   hexo g
   ```

3. 自动生成网站静态文件，并部署到设定的仓库。

   ```
   hexo d
   ```

   



