git库 存储了很多关于资源库历史记录的相关信息（在.git隐藏目录中，使用ls -a可以查看）

1,初始化或创建新的git仓库
    git init (此时使用ls -a可以看到当前目录下有.git文件夹)
    
    git log  查看当前的commit信息
    
    git log --stat 查看最近提交的commit（比git log详细）
    
    git status 查看当前分支状态
    
    git log origin/master  查看你想看的分支log
    
2,staging area :为允许明确指定要提交的更改

    git add   file_name(添加需要commit的文件到staging area)
    git reset file_name(删除从staging area中的file_name)
    
    举例：
        (py3) [c02419@c02419-pc git_test]$ git add aa.txt bb.txt 
        (py3) [c02419@c02419-pc git_test]$ git status
        位于分支 master

        尚无提交

        要提交的变更：
          （使用 "git rm --cached <文件>..." 以取消暂存）

            新文件：   aa.txt
            新文件：   bb.txt

        未跟踪的文件:
          （使用 "git add <文件>..." 以包含要提交的内容）

            cc.txt

3,commit (提交)与编写提交信息

    git commit
    git commit -m "commit message"

4, git diff (对比工作目录与staging area)

   git diff --staged (对比staging area 和 git库)
   
   git diff master origin/master  对比两个分支的diff
   
   
   ![image](https://github.com/ainingxiaoguai/learn-git/blob/master/git_diff.png)
   
   
   
   git reset --hard (放弃工作目录或staging area 的更改)

5，查看当前分支

    git branch(也可以用git status查看)
    
    git branch -a  （查看所有分支情况 可以看到origin/master 等 git branch看不到的分支）
    
6,新建分支

    git branch branch_name
    
    
7,切换到分支

    git checkout branch_name
    
8,直观查看分支结构

    git log --graph --oneline branch_name1 branch_name2
    
9,checkout 一个 commit 会有提示 “detached HEAD”,此时使用 

        git checkout -b new_branch_name(该命令等于 git branch new_branch_name; git checkout new_branch_name)
        
10,如果删除某个分支并导致无法从现有的分支访问一些提交，则在 Git 的垃圾收集过程运行之前，仍可继续通过提交 ID 访问这些提交。
    除非你主动关闭此过程，否则它将不时自动运行。也可以通过命令 git gc 手动运行此过程。
    
11,合并分支

    git merge master coins
  合并后，两个分支中的commit按照时间排序，可以使用git show  commit_id 来查看你想看某个commit的更改，而不用之前git diff old_file new_file
  在合并分支后，可以删除多余的分支 
     git branch dash d coins(这不会删除commit，只会删除分支标签)
     
12,合并冲突 

    git merge --abort   将文件恢复到你开始合并之前的状态
 
    git config --global core.autocrlf true  合并冲突（Windows 与 Unix 系统之间的换行符）
    
13, git log -n num 表示列出多少个commit

14, git branch -d branch_name 删除分支标签
