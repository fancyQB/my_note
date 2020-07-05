# git用法		

### 一. git连接github



> https://blog.csdn.net/u012037852/article/details/80756081

#### 1. 本地配置

​		配置使用如下命令:

```
git config --global user.name 'your name'
git config --global user.email 'your email'
```

注意: 
git config命令的–global参数，用了这个参数，表示你这台机器上所有的 Git 仓库都会使用这个配置，当然也可以对某个仓库指定不同的用户名和 Email 地址(如需要, 可自行搜索)。

#### 2.连接github或者码云

1.生成ssh公钥:

```
ssh-keygen -t rsa -C "email@example.com"  
# Generating public/private rsa key pair...
```

\# 三次回车即可生成 ssh key, 这里的邮箱最好填和刚才一样的
然后用文本编辑器(如notepad)打开id_rsa.pub这个文件, 全选复制.

2.接下来到GitHub上，打开“Account settings”--“SSH Keys”页面，然后点“Add SSH Key”，填上Title（随意写），在Key文本框里粘贴 id_rsa.pub文件里的全部内容。

3.验证是否成功，在git bash里输入下面的命令
$ ssh -T git@github.com
如果初次设置的话，会出现如下界面，输入yes 同意即可

#### 3.初始化本地仓库

I: 在你要提交的目录下, git init 
II: 和远程刚创建的仓库连接, git remote add origin git@github.com:xxx/matlablearning.git 
III: push前先将远程repository的修改pull(拉)下来, 避免之前本地仓库和远程仓库不一致, 导致提交出错! 
git pull origin master 

#### 4.做出本地修改并提交

git add. #将添加的提交到列表上

git commit -m '提交的信息'

git push orign master #发送到你提交的github上

git status #查看git状态

### 二.git删除远程仓库文件

#### 1.预览将要删除的文件

```
git rm -r -n --cached 文件/文件名称
加上-n这个参数.执行命令时,是不会删除任何文件的,展示此命令要删除的文件预览
```

#### 2.确定无误后删除文件

```
git rm -r --cached 文件/文件名
```

#### 3.提交到本地并推到远程服务器

```
git commit -m '提交哦说明'
git push origin master
```

4. #### 删除远端服务器命令

```
git remote remove origin
```

