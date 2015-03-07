<h2>git-learning</h2>
http://git-scm.com/book/zh/ch4-7.html
----
如何使用git（只介绍常用的操作）

Git 分支管理详解  
    链接：http://www.topthink.com/topic/727.html   
          http://blog.csdn.net/kasagawa/article/details/6797812   
  
  

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
   

##【个人开发模式】
----
Git本地仓库的搭建:  
 $ cd myproject  
 $ git init .  
 $ git add <files> ...    //通常在当前目录下创建即可，也可以像服务器一样  
 $ git commit -m ‘initial commit’  


##【常用操作】
----
  查看分支 git branch -a  
  创建分支 git branch name  
  切换分支 git checkout name  
  创建并切换 git checkout -b name  
  合并某分支到当前分支 git merge name   
  推送到服务器 git push <remote> <local branch>:<remote branch>  
  拉取到本地 git pull <remote> <remote branch>:<local branch>  
  删除分支 git branch -d name  
  撤销操作 git revert <commit log string>  
  撤销提交 git reset  
  查看缓存状态 git status  
  查看分支提交历史 git log  
  比较差异 git diff
  查找共同祖先并比较差异（查看实际提交的代码） git diff master...contrib
  
  
  git revert：回退某次提交，并重新提交，相当于代码恢复修改前，但是服务器上有两次提交log  
  git reset：回退某次提交，同时回退修改log，但是修改内容回退到本地暂存区，由用户确定丢弃（checkout）或者重新提交  
  
  git reset简介： http://blog.csdn.net/hudashi/article/details/7664464  
  git revert和git reset的区别: http://blog.csdn.net/hudashi/article/details/7664460  

如果开发者都可以拥有访问权限，可以建立一个统一的用户（如git），开发者将各自的pub放在git的.ssh/auth_****里，则可以通过ssh对仓库进行读写访问。 
如果需要开发者访问权限，可以有两种方式来实现对仓库的访问权限：一种是由操作系统提供，另一种是由专门的基于git的版本管理软件。  
1、操作系统提供
    在服务器上给需要参与的开发者创建帐户，并分类到具体的项目组里。给仓库所在目录限定组群的访问权限，限定指定群组的开发者才只可以对仓库内的文件进行只读或读写。这样自然就只有被加入这个项目组的开发者才有权限在仓库内pull或push操作。
    优点：本质安全（设系统是安全的）。
    缺点：权限划分粒度不够细致，只能对一个组一起设定，不能在组内进行个例限定权限。 
2、git版本管理软件  
    基于git的版本管理软件如gitLab、gitosis、gitolite等。  
    gitLab: 类似于github，可以通过web进行控制。  
            http://blog.csdn.net/zy416548283/article/details/38057925   
            http://herry2013git.blog.163.com/blog/static/219568011201341111240751   
    gitosis: 权限可以细化到一个用户的读写权限（push和pull），安装方便。  
             http://git-scm.com/book/zh/ch4-7.html    
    gitolite: 权限可以细化用一个用户对一个分支或标签的读写权限（push和pull），安装配置较为复杂。   
              http://git-scm.com/book/zh/v1/%E6%9C%8D%E5%8A%A1%E5%99%A8%E4%B8%8A%E7%9A%84-Git-Gitolite  

