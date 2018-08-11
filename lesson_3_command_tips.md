1,查看或创建远程仓库

   git remote 查看
   git remote add orign URL  创建名为orign的远程仓库，地址是URL
   git remote -V 详细查看
   
2,向远程仓库提交更改
   git push origin master
   
3,从远程仓库提取
   git pull origin master
   ![image](https://github.com/ainingxiaoguai/learn-git/blob/master/git_pull.png)
   
   
   git clone URL 无法克隆没有commit的远程仓库

4, fast-forward merges
      可以从b到a，则是fast-forward merges
