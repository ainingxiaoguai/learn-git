git库 存储了很多关于资源库历史记录的相关信息（在.git隐藏目录中，使用ls -a可以查看）

1,初始化或创建新的git仓库
    git init (此时使用ls -a可以看到当前目录下有.git文件夹)
    git log  查看当前的commit信息
    git status 查看最近提交的commit（比git log详细）
    
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
   
   
   ![image](https://github.com/ainingxiaoguai/learn-git/blob/master/git_diff.png)
   
   
   
   git reset --hard (放弃工作目录或staging area 的更改)

5，查看当前分支

    git branch(也可以用git status查看)
    
6,新建分支
    git branch branch_name
    
7,切换到分支
    git checkout branch_name
    
8,直观查看分支结构
    git log --graph --oneline branch_name1 branch_name2
    
    
