---
title: 'Host Multple Blog on one Github Pages'
date: 2016-05-06 15:50:46 +0800
comments: true
categories: 
- Hexo
- Blog
- Markdown

---
不同Blog想要放在同個Github Page...?

<!--more-->

1. 建立Repo. Ex. https://github.com/jimmyliao/Life.git
2. 裡面新增一個source branch
3. 最簡單的方法，新增index.html
(optional) 或是把原本site generator(例如hexo)搬同樣一份, 請見步驟4

4. 
4.1 clone一份Project repo, 方便起見還是在remote設定gh-pages & source, gh-pages就是最後發布的branch. 請見 Ref #1
4.2 

``` bash
$ mkdir hexo
$ cd hexo
$ hexo init
INFO  Cloning hexo-starter to ~/WebDrive/GitHub/Blogging/Life.git/blog_src
Cloning into '/Users/jimmyliao/WebDrive/GitHub/Blogging/Life.git/blog_src'...
remote: Counting objects: 53, done.
remote: Total 53 (delta 0), reused 0 (delta 0), pack-reused 53
Unpacking objects: 100% (53/53), done.
Checking connectivity... done.
Submodule 'themes/landscape' (https://github.com/hexojs/hexo-theme-landscape.git) registered for path 'themes/landscape'
Cloning into 'themes/landscape'...
remote: Counting objects: 730, done.
remote: Total 730 (delta 0), reused 0 (delta 0), pack-reused 730
Receiving objects: 100% (730/730), 2.51 MiB | 955.00 KiB/s, done.
Resolving deltas: 100% (384/384), done.
Checking connectivity... done.
Submodule path 'themes/landscape': checked out 'decdc2d9956776cbe95420ae94bac87e22468d38'
INFO  Install dependencies
...

  `-- serve-static@1.10.2
    +-- escape-html@1.0.3
    `-- send@0.13.1
      +-- destroy@1.0.4
      +-- etag@1.7.0
      +-- fresh@0.3.0
      +-- http-errors@1.3.1
      +-- range-parser@1.0.3
      `-- statuses@1.2.1
INFO  Start blogging with Hexo!

``` 

產生template之後

``` bash
$ hexo g
...
INFO  28 files generated in 648 ms
``` 
記得修改一下_config.yml
``` 
url: http://jimmyliao.github.io/Life
root: /Life/

...
deploy:
  type: git
  repo: https://github.com/jimmyliao/Life.git
branch: gh-pages

``` 

``` bash
$ npm install hexo-deployer-git --save #裝一下deployer
$ npm install hexo-renderer-stylus --save #裝一下不然會整個css破掉, hexo issue
$ hexo d
...
To https://github.com/jimmyliao/Life.git
 + 541ea14...4eb6485 HEAD -> gh-pages (forced update)
Branch master set up to track remote branch gh-pages from https://github.com/jimmyliao/Life.git.
INFO  Deploy done: git


``` 


5. 測試.

http://jimmyliao.github.io -> 主站
http://jimmyliao.github.io/Life -> 利用Project Pages新增的


P.S. 不過我開這麼多個，也沒在寫Blog啊


Ref.
#1. https://help.github.com/articles/user-organization-and-project-pages/