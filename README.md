<h2>git-learning</h2>
----
如何使用git（只介绍常用的操作）


##【团队开发模式】
----
Git服务器仓库的搭建:
  $ mkdir project.git
  $ cd project.git
  $ git init –bare
  
  在一个开发人员的电脑上
 $ cd myproject
 $ git init
 $ git add <files> ...
 $ git commit -m ‘initial commit’
  关联远程分支
 $ git remote add <remote> <url>
  推送第一个版本
 $ git push origin master
 
 Git 分支管理详解
    链接：http://www.topthink.com/topic/727.html
  
  
##【个人开发模式】
----
Git本地仓库的搭建:
 $ cd myproject
 $ git init .
 $ git add <files> ...    //通常在当前目录下创建即可，也可以像服务器一样
 $ git commit -m ‘initial commit’


##【常用操作】
----
