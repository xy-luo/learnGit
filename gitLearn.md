``git init``  
把目录变成一个git可管理的仓库（.git目录，用来跟踪管理版本库）
<br>

``git add readme.txt``  
``git commit -m "wrote a readme file."``  
add：文件从 工作区 --> 暂存区  
commit：文件从 暂存区 --> 仓库
* git add可以一次添加多个文件
* git commit一次性提交暂存区所有文件 到当前分支  
eg. git add file1.txt file2.txt  
    git commit -m "add 2 files"
<br>

``git status``
查看仓库当前状态

``git diff``, ``git diff readme.txt``
查看此文件上次的修改

``git log``, ``git log --pretty=online``
显示从最近到最远的提交日志（提交历史）

把版本回退到上一个版本
``git reset --hard HEAD^``
此时再查看``git log``已经看不到之前最后一个版本了，要想回到回退前最后那个版本：
``git reset --hard 版本号(808014c)``
不知道commit id怎么回到回退前最后那个版本？
``git reflog``查看每次git命令记录

HEAD表示当前版本
HEAD^表示上一个版本
HEAD^^表示上上个版本
HEAD～10往上10个版本

查看当前文件内容
``cat readme.txt``

``git diff HEAD -- readme.txt``
查看工作区 和 版本库 里最新版本的区别

``git checkout -- readme.txt``
针对文件还未git add前的撤销(丢掉工作区的修改)
把readme.txt在工作区的修改全部撤销（两种情况--让文件回到最近一次git commit或git add时的状态）
1. readme.txt被修改后 还未放进暂存区。撤销修改 即 回到和版本库一模一样的操作
2. readme.txt被修改后 已添加到暂存区。然后又做了修改。 此时撤销修改 即 回到添加到暂存区后的状态


已经把文件git add
``git reset HEAD readme.txt``
可以把暂存区的修改撤销掉（unstage），重新放回工作区

场景1：当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，用命令git checkout -- file。

场景2：当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改，分两步，第一步用命令git reset HEAD <file>，就回到了场景1，第二步按场景1操作。

场景3：已经提交了不合适的修改到版本库时，想要撤销本次提交，参考版本回退，不过前提是没有推送到远程库。
    
    
    

删除文件
在工作区删除文件：``rm test.txt``
此时工作区和版本库不一样
``git rm test.txt``
``git commit -m "remove test.txt``
删错了恢复
``git checkout -- test.txt``
    

``git push -u origin master``
``git merge dev``
``git checkout -b dev`` 
= ``git branch dev`` + ``git checkout dev`` / ``git switch dev``
= ``git switch -c dev``


commit id是SHA1计算出来的十六进制数
Working directory 工作区
Repository 版本库
index/stage 暂存区


git rebase

cat .git/HEAD

git 非使用指令
``git help -a``
``git help -g``
``git config --list``
``git config --global``
``git config --edit``



following command and follow the instructions in your editor to edit
your configuration file:

    git config --global --edit

After doing this, you may fix the identity used for this commit with:

    git commit --amend --reset-author




terminal command
``mkdir learnGit``  
``ls``, ``ls -ah``  
``vi readme.txt`` --> press ``esc`` --> enter ``:wq`` --> press ``回车``
``vim readme.txt``修改这个文件
