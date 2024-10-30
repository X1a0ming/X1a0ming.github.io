---
title: 使用git仓库进行hexo多设备同步
date: 2024-10-30 22:33:18
tags:[hexo, git]
categories: [hexo]
---

## 背景

在使用hexo写博客的时候，如果只在一台设备上写博客，那么就没有什么问题。但是如果有多台设备，那么就会出现同步的问题。这时候就可以使用git仓库来解决这个问题。

## 步骤

0. 默认已经安装好了hexo，git，nodejs，npm等环境，并且部署在github上。

1. 在本地hexo目录下，初始化git仓库。

```bash
git init
```

2. 添加远程仓库。

```bash
git remote add origin https://github.com/your-username/your-repo.git
```

3. 新建一个分支，用来存放hexo的源文件。

```bash
git checkout -b hexo
```

4. 将hexo的源文件放到这个分支上。

```bash
git add .
git commit -m "init"
git push origin hexo
```

5. 在其他设备上，clone这个仓库。

```bash
git clone
```

6. 切换到hexo分支。

```bash
git checkout hexo
```

7. 在这个分支上，完成hexo部署就可以写博客了。当然，写完之后，要提交到远程仓库。

```bash
git add .
git commit -m "add new post"
git push origin hexo
```

## 其他

踩坑：在本地错误创建了一个master分支，然后在github上创建了一个hexo分支。

无伤大雅，只是在push的时候，要指定分支。

```bash
git push origin master:hexo
```
