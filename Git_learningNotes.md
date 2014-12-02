---
title: "Git"
author: "qiandu"
date: "Tuesday, December 02, 2014"
output: html_document
---
----
####Git的origin和master

- `git remote -v`查看远程repository

- `git branch -a`查看所有分支，包括本地和远程

- `git push origin master`在local repository中找到名为master的分支，并用它更新remote repository下名字为master的分支，如果没有就创建它

> 其实这里master是一个“refspec”,正常的refspec是<src>:<dst>,冒号前面是local branch名字，后面是remote branch,如果省略dst，就认为与src相同，上面等价于：git push origin/master:master;
git push origin :master用空更新branch相当于删除了master

```
git config --global user.name = babyang
git config --global user.email = isbabyang@gmail.com
#记住密码
git config --global credential.helper wincred
```
