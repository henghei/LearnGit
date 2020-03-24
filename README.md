## git对本地库的管理

## git->github（远程仓库）
* 在公司是实现多人分工合作的都会用到github，github就是我们的远程仓库（需注册）  
[github地址](https://github.com)
* 本地库与远程仓库初次建立连接需要ssh密钥，查看本地git库是否有.ssh/文件夹，若无执行以下命令生成一对密钥
```
$ ssh-keygen -t rsa -C "youremail@example.com"
```
* 之后会要求确认路径和输入密码，我们这使用默认的一路回车就行。成功的话会在 ~/ 下生成 .ssh 文件夹，进去，打开 id_rsa.pub，复制里面的 key回到 github 上，进入 Account => Settings（账户配置）,选择 SSH and GPG keys，然后点击 New SSH key 按钮,title 设置标题，可以随便填，粘贴在你电脑上生成的 key
* 为了验证是否成功，输入以下命令：
```
$ ssh -T git@github.com
```
* 提示Hi tianqixin! You've successfully authenticated, but GitHub does not provide shell access.命令说明我们已成功连上 Github
* 在github创建新的仓库，之后就可以根据新仓库提示在本地仓库运行命令
1. 本地仓库获取github的更新信息
* 从远程仓库下载新分支与数据：  
git fetch  
* 从远端仓库提取数据并尝试合并到当前分支  
git merge  
2. github获取本地的更新信息
* 修改本地库文件
* git add .
* git commit -m'备注'
* git push -u origin master（第一次push一定要这样写，第二次就可以直接git push）


## git 基本操作
* git init
* 查看路径下的文件命令（ls）及隐藏文件（ls -a）
* git clone
```
 git clone [url]
 ```
 * git add . （将文件添加到缓存）
 * git reset HEAD '取消已缓存的文件名'（用于取消已缓存的内容）
 * git status 命令用于查看项目的当前状态（是否修改、提交）
 * git diff（显示已写入缓存与已修改但尚未写入缓存的改动的区别）
 * git commit（将缓存区内容添加到仓库中）（Git 为你的每一个提交都记录你的名字与电子邮箱地址，所以第一步需要配置用户名和邮箱地址）
 ```
 $ git config --global user.name 'runoob'
$ git config --global user.email test@runoob.com
```
* 删除目录文件命令  
  git rm <file>
 * 强制删除文件命令  
git rm -f <file>
 * 递归删除（进入某个目录中，执行此语句，会删除该目录下的所有文件和子目录。）  
 git rm –r *
 * git mv （用于移动或重命名一个文件、目录、软连接）
 ```
 $ git mv README  README.md
 ```
 


## 创建版本库
* **第一步**：何为版本库？就是仓库（repository），这样之后的所有操作就会被git跟踪管理了（注意：在windows系统下为了避免不必要的麻烦，所有的文件名不准出现中文）
```
$ mkdir learngit
$ cd learngit
$ pwd
/Users/michael/learngit
```
* pwd命令用于显示当前打开文件的所在路径
* **第二步**git init把这个目录变成Git可以管理的仓库(此时git可以正式跟踪管理文件的变动)
```
$ git init
Initialized empty Git repository in /Users/michael/learngit/.git/
```
* 当前目录下多了一个.git的目录，这个目录是Git来跟踪管理版本库的，没事千万不要手动修改这个目录里面的文件，不然改乱了，就把Git仓库给破坏了。
如果你没有看到.git目录，那是因为这个目录默认是隐藏的，用ls -ah/ls -a命令就可以看见。
* 创建新文件
```
touch readme.txt
```
* 填充内容然后git add .（告诉Git，把文件添加到仓库：）
* git commit -m'xxxx'(告诉Git，把文件提交到仓库：可以add 多次，最后在commit一次)



## Git安装
* 默认安装就可以，安装完毕在开始菜单栏查找Git->Git Bash点击运行，安装成功  
[git下载地址](https://git-scm.com/downloads)
* 安装完需要进一步设置，在命令行输入以下内容：(注意git config命令的--global参数，用了这个参数，表示你这台机器上所有的Git仓库都会使用这个配置)  
```
$ git config --global user.name "Your Name"
$ git config --global user.email "email@example.com"
```

