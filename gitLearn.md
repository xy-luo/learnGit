## some question
1. 本地rm <file>, 然后add + commit 和 git rm <file> + commit有什么区别？


## 本地Git操作
### Git init
``git init``  
把目录变成一个git可管理的仓库（.git目录，用来跟踪管理版本库）


### Add & Commit 
``git add readme.txt``  
**add**：文件从 工作区 --> 暂存区   
``git commit -m "wrote a readme file."``   
**commit**：文件从 暂存区 --> 仓库

* git add可以一次添加多个文件
* git commit一次性提交暂存区所有文件 到当前分支  
&nbsp;**eg.** git add file1.txt file2.txt  
&emsp;&emsp;  git commit -m "add 2 files"


### Git中查看信息
``git status``  
查看仓库当前状态

``git diff``, ``git diff readme.txt``  
查看此文件上次的修改；  
``git diff HEAD -- readme.txt``  
查看版本库 和 工作区 里最新版本的区别。

``git log``, ``git log --pretty=online``  
显示从最近到最远的提交日志（提交历史）


### Git中版本回退
``git reset --hard HEAD^``  
把版本回退到上一个版本。此时再查看``git log``已经看不到之前最后一个版本了。  
要想回到回退前最后那个版本：  
``git reset --hard 版本号(808014c)``  
不知道commit id怎么回到回退前最后那个版本？
``git reflog``查看每次git命令记录

- HEAD表示当前版本  
- HEAD^表示上一个版本  
- HEAD^^表示上上个版本  
- HEAD～10往上10个版本  


### Git中的撤销修改
> 场景1：当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改；—— **修改，未add**  
> 场景2：当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改；—— **修改，add，未commit**  
> 场景3：已经提交了不合适的修改到版本库时，想要撤销本次提交。—— **修改，add，commit**  

#### 一、撤销工作区的修改  
``git checkout -- readme.txt``  
撤销工作区readme.txt文件的修改，让文件回到最近一次git commit或git add时的状态（即：暂存区有文件恢复到暂存区文件状态，暂存区无文件恢复到版本库文件状态）
1. readme.txt被修改后 未add进暂存区。撤销修改 即 回到和版本库一模一样的操作
2. readme.txt被修改后 已add到暂存区；然后又做了修改。 此时撤销修改 即 回到添加到暂存区后的状态

#### 二、撤销暂存区的修改
``git reset HEAD readme.txt``
可以把暂存区的修改撤销掉（unstage），重新放回工作区

> 场景1：当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时：  
> Ans：直接撤销工作区文件修改 `git checkout -- file`。  
> 
> 场景2：当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改：  
> Ans：分两步，先撤销暂存区的修改，再撤销工作区的修改。`git reset HEAD <file>`，就回到了场景1，`git checkout -- file`。  
> 
> **场景3：已经提交了不合适的修改到版本库时，想要撤销本次提交：**  
> Ans：参考版本回退，不过前提是没有推送到远程库。


### 删除文件
在工作区删除文件：``rm test.txt``
此时工作区和版本库不一样   
1. 在版本库也删除该文件  
``git rm test.txt`` + ``git commit -m "remove test.txt``
2. 删错了恢复  
``git checkout -- test.txt``
    

## 远程仓库
``git push -u origin master``
``git merge dev``
``git checkout -b dev`` 
= ``git branch dev`` + ``git checkout dev`` / ``git switch dev``
= ``git switch -c dev``






### Git基本知识
commit id是SHA1计算出来的十六进制数；  
Working directory 工作区；  
index/stage 暂存区；  
Repository 版本库  



git rebase
<br>

cat .git/HEAD
<br>

git 其他指令：
- ``git help -a``
- ``git help -g``
- ``git config --list``
- ``git config --global``
- ``git config --edit``


<br>
following command and follow the instructions in your editor to edit
your configuration file:

    git config --global --edit

After doing this, you may fix the identity used for this commit with:

    git commit --amend --reset-author
<br>



## terminal command
``mkdir learnGit`` make directory新建一个目录
  
``cat readme.txt`` 查看当前文件内容  

``vi readme.txt`` --> press ``esc`` --> enter ``:wq`` --> press ``回车``  
创建文件


`pwd` print working directory显示当前命令所处于的位置.  

`ls` list查看目录下的内容  
加入参数:  
1. `ls -l`: 目录下内容的详细信息
2. `ls -la`: 查询子文件 .表示文件夹内的隐藏文件
3. `ls -ah`: 文件夹中的隐藏文件

`cd` change directory进入一个指定的目录
1. …/表示上一层目录
2. ./表示当前的目录
3. 文件夹的结尾需要/
4. 可以用Tab完成文件名的补全
    
`mv` move重命名或者移动文件/目录
（重命名 mv name change_name)
（移动 mv file floder/)
    
`cp` copy复制文件/目录
（复制文件夹时，需要增加参数-R 其实质上是进行了递归的操作）
（cp -R floder change_floder)
    
``rm readme.txt`` remove删除文件/目录
（rm -f 无条件删除）
（rm -R删除文件夹）
（rm -fR无条件删除文件夹）
（rm -fR *删除当前文件夹的所有内容）
    
`du -sh` disk usage查看文件/目录的大小

`man` manual pages查看命令的帮助信息
    
`touch` 创建文件
（word .docx）
（文本编辑 .tex）
（需要设置创建文件的格式）
    
`open` 打开文件
    
`vim readme.txt` 打开/编辑文本文件
    
`find` 查找文件
（正则表达式）
（*为通配符 代表任意的字符）
（-name 以名称的形式去搜索）
（目录的路径需要加上/ 以/结尾）
    
`file` 查看文件的类型
    
`cd ～` 快速进入用户的主文件夹目录
（～代表用户主文件夹目录）

control+C 中断命令的进行<br>
control+A 光标回到行头<br>
control+E 光标回到行尾<br>
