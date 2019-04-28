### 一 本地创建repo
```
git init
git add *.c
git commit -m 'initial project version'
```

### 二 克隆一个repo
```
git clone https://github.com/libgit2/libgit2
```

### 三 常用操作
```
//只从git里删除，不删除文件本身
git rm --cached file.txt
//git mv
git mv = mv + git rm + git add
//显示远程仓库对应的Url
git remote -v 
// 添加远程仓库
git remote add <shortname> <url>
```

### 四 分支
```
//查看分支，一般加上-vv
git branch -vv
//查看远程分支
git ls-remote
//查看分支图(下面有更完善的例子，见alias)
git log --oneline --decorate --graph --all
//创建分支
git branch testing
//切换分支
git checkout testing
//创建并切换分支
git checkout -b iss53
//创建远程分支并提交
git push --set-upstream origin learntest2
//删除远程分支
git push origin --delete Chapater6
//删除本地分支
git branch -d Chapater8
//合并分支
git merge hotfix
//同步远程仓库到本地
git fetch origin
//git pull
git pull = git fetch + git merge
//设置跟踪的远程分支-u = --set-upstream-to
git branch -u origin/serverfix
```

### 五 别名：
```
// 简要版
git config --global alias.graph "log --oneline --decorate --graph --all"
// 丰富版
git config --global alias.graph "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"
```
### 六 submodule
```
//添加子模块
git submodule add https://github.com/chaconinc/DbConnector
git clone含子模块的project，会生成子模块路径，但没有相关文件。还需执行git submodule init和git submodule update。或者git clone xx --recursive
//更新子模块
git submodule update --remote
```