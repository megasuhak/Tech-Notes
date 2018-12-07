
#### Git 常用命令

##### 新建代码库
1. 在当前目录新建一个Git代码库
`git init`

##### 签出代码库

git clone https://github.com/xuyixing/my_record.git

3.

4.


##### 配置

git config --global user.name xuyixing
git config --global user.email raynorxyx@hotmail.com
git config --global user.password passwordGit123456

##### 增加/删除文件


##### 代码提交


git status


git log



git config --list


git clone

`强制覆盖本地文件`
git fetch --all
git reset --hard
git pull



```
//查看tag
git tag  

//在某个commit版本号 上打tag
git tag Tag_20181207 7c2e57

//本地的tag标签push到代码库
git push origin 20181207

```


```
start a working area (see also: git help tutorial)
   clone      Clone a repository into a new directory
   init       Create an empty Git repository or reinitialize an existing one

work on the current change (see also: git help everyday)
   add        Add file contents to the index
   mv         Move or rename a file, a directory, or a symlink
   reset      Reset current HEAD to the specified state
   rm         Remove files from the working tree and from the index

examine the history and state (see also: git help revisions)
   bisect     Use binary search to find the commit that introduced a bug
   grep       Print lines matching a pattern
   log        Show commit logs
   show       Show various types of objects
   status     Show the working tree status

grow, mark and tweak your common history
   branch     List, create, or delete branches
   checkout   Switch branches or restore working tree files
   commit     Record changes to the repository
   diff       Show changes between commits, commit and working tree, etc
   merge      Join two or more development histories together
   rebase     Reapply commits on top of another base tip
   tag        Create, list, delete or verify a tag object signed with GPG

collaborate (see also: git help workflows)
   fetch      Download objects and refs from another repository
   pull       Fetch from and integrate with another repository or a local branch
   push       Update remote refs along with associated objects

```
