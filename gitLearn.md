``git init``  
把目录变成一个git可管理的仓库（.git目录，用来跟踪管理版本库）
<br>

``git add readme.txt``  
``git commit -m "wrote a readme file."``  
add：文件从 工作区 --> 暂存区  
commit：文件从 暂存区 --> 仓库
<br>

``git status``


``git diff readme.txt``
``git log``, ``git log --pretty=online``
``git reflog``
``git checkout``
``git reset``
``git rm``
``git push -u origin master``
``git merge dev``
``git checkout -b dev`` 
= ``git branch dev`` + ``git checkout dev`` / ``git switch dev``
= ``git switch -c dev``


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
