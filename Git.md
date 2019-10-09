# 1. Git安装步骤详细

1.  开始安装

   ![1](.\image\Git\1.png)

2.  选择安装路径

   ![2](.\image\Git\2.png)

3. 选择组件

   ![3](.\image\Git\3.png)

- Additional icons 附加图标
  
- On the Desktop 在桌面上
  
- Windows Explorer integration Windows资源管理器集成鼠标右键菜单
  - Git Bash Here
  - Git GUI Here

- Git LFS (Large File Support) 大文件支持

- Associate .git* configuration files with the default text editor 

  将 .git 配置文件与默认文本编辑器相关联

- Associate .sh files to be run with Bash  

  将.sh文件关联到Bash运行

- Use a TrueType font in all console windows

  在所有控制台窗口中使用TrueType字体

- Check daily for Git for Windows updates

  每天检查Git是否有Windows更新

4. 是否创建开始菜单目录

   ![4](.\image\Git\4.png)

5. 选择默认编辑器

   ![5](.\image\Git\5.png)

6.  cmd可以执行git命令

   ![6](.\image\Git\6.png)

7.   

   ![7](.\image\Git\7.png)

8.  

   ![8](.\image\Git\8.png)

9.  

   ![9](.\image\Git\9.png)

10.  

    ![10](.\image\Git\10.png)

11. 安装

    ![11](.\image\Git\11.png)

12. 安装过程，等

    ![12](.\image\Git\12.png)

13.  安装完成

    ![13](.\image\Git\13.png)



# 2. Git的使用

1. 因为Git是分布式版本控制系统，所以需要填写用户名和邮箱作为一个标识，右键，git bash here输入以下命令

    ```
    $ git config --global user.name "Your Name"
    $ git config --global user.email "email@example.com"
    ```

    - **--global参数**：表示你这台机器上所有的Git仓库都会使用这个配置，当然也可以对某个仓库指定不同的用户名和Email地址。

    

    创建git目录

    ```
    $ mkdir git
    ```

    显示当前路径

    ```
    $ pwd
    ```

    进入到git目录

    ```
    $ cd git
    ```

    把该目录变成Git可以管理的仓库

    ```
    $ git init
    ```

    把文本文件 readme.txt添加到仓库，可以添加多个文件

    ```
    $ git add readme.txt
    ```

    提交到仓库，-m参数后面输入的是本次提交的说明

    ```
    $ git commit -m "wrote a readme file"
    ```

    查看工作区和暂存区中文件的区别

    ```
    git diff readme.txt
    ```

    查看提交日志，--pretty=oneline（不加上则是查看详细信息）

    ```
    git log --pretty=oneline
    ```

    回退到上一个版本，上上个版本则是HEAD^^

    ```
    $ git reset --hard HEAD^
    ```

    撤销修改，（自修改后还没有被放到暂存区，还没有add）

    ```
     git checkout -- b.txt
    ```

    撤销修改，（add放到暂存区，还没有commit）

    ```
    git reset HEAD b.txt
    ```

    删除文件，

    ```
    rm test.txt
    ```

    一是确实要从版本库中删除该文件，那就用命令`git rm`删掉，并且`git commit`：

    ```
    git rm b.txt
    git commit -m "说明"
    ```

    二是误删了，则恢复

    ```
    git checkout -- test.txt
    ```


### 远程仓库

1. 创建秘钥

    ```
    $ ssh-keygen -t rsa -C "youremail@example.com"
    ```

    - 创建之后在**C:\Users\Administrator\.ssh**目录会有一个**id_rsa.pub**文件，这是公钥，把公钥添加到Github上的settings中的SSH and GPG kys中的**SSH Keys**

2. 在github上创建一个新的仓库hello

3. 关联本地仓库

   ```
   $ git remote add origin git@github.com:michaelliao/learngit.git
   ```

4. 推送master分支

   ```
   $ git push -u origin master
   ```

   由于远程库是空的，我们第一次推送`master`分支时，加上了`-u`参数，Git不但会把本地的`master`分支内容推送的远程新的`master`分支，还会把本地的`master`分支和远程的`master`分支关联起来，在以后的推送或者拉取时就可以简化命令。

5. 以后提交

   ```
   $ git push origin master
   ```

### 克隆仓库

```
git clone 仓库地址
```

### 分支管理

创建dev分支，`-b`参数表示创建并切换

```
$ git checkout -b dev
```

```
$ git branch dev
$ git checkout dev
```

查看分支

```
git branch
```

切换分支

```
git checkout master
```

合并dev分支

```
git merge dev
```

删除dev分支

```
git branch -d dev
```

创建并使用分支，新版本可以使用

```
git switch -c dev
```

切换分支，新版本可以使用

```
git switch master
```

### 分支冲突

查看分支的合并情况

```
git log --graph --pretty=oneline --abbrev-commit
```

删除分支

```
git branch -d f1
```

# 3. Github删除仓库

1. 打开你的仓库

   ![1](.\image\Github\1.png)

2. 点击你的其中某一个仓库进入详情

3. 点击**settings**

   ![2](.\image\Github\2.png)

4. 拉倒最下面，有个删除这个仓库的选项

   ![3](.\image\Github\3.png)

5. 然后弹出一个框，需要你输入这个仓库名，确保没有删错

   ![4](.\image\Github\4.png)

6. 然后输入Github密码，确保是本人登录

   ![5](.\image\Github\5.png)

7. 然后就删除了

# 4. 把本地仓库上传到github

1. 先把本地的一个目录变成git可管理的仓库，

   ```
   git init
   ```

2. 添加该目录下的所有文件以及目录到暂存区

   ```
   git add .
   ```

3.  提交

   ```
   git commit -m "说明注释"
   ```

4. 本人已经设置过SSH KEY了，这里不再重复

5. 在Github添加一个仓库（Repository），

   Repository name：项目名

   Description (optional)：项目描述

6. 勾选这个，会在仓库生成一个说明文件

   ![6](.\image\Github\6.png)

7. 创建好之后，复制SSH地址

8. 关联

   ```
   git remote add origin git@github.com:hyzhben/Study2019.git
   ```

9. 推送

   ```
   git push -u origin master
   ```

10. 失败，因为创建的不是空的仓库，所以需要先把说明文档下下来，完了再执行第9步

    ```
    git pull --rebase origin master
    ```

11. 第一次提交需要加上**-u**参数，以后就不用了

    ```
    git push origin master
    ```

12. 注意：是git管理仓库的目录下的内容不会同步

# 5.一些指令

### 查看你的Git配置命令

```
git config --list
```

# 6. 配置忽略文件.gitignore

1. **.gitignore**文件是告诉Git哪些文件不需要添加到版本管理中，如项目中的npm包（node_modules）

2. 创建**.gitignore**文件（常规Window操作）

   - 直接创建会提示你必须写上文件名

   - 先创建**gitignore.txt**

   - 再用命令重命名**ren gitignore.txt .gitignore**

3. 创建**.gitignore**文件（使用git bash）

   - 根目录下右键选择“Git Bash Here”进入bash命令窗口；

   - 输入**vim .gitignore**或touch .gitignore命令，打开文件（没有文件会自动创建）；

   - 按i键切换到编辑状态，输入规则，例如node_modules/，然后按Esc键退出编辑，输入:wq保存退出。

4. 常用规则

   ```
   /mtk/ 过滤整个文件夹
   *.zip 过滤所有.zip文件
   /mtk/do.c 过滤某个具体文件
   
   !src/   不过滤该文件夹
   !*.zip   不过滤所有.zip文件
   !/mtk/do.c 不过滤该文件
   ```

5. 通配符

   以斜杠`/`开头表示目录；
   以星号`*`通配多个字符；
   以问号`?`通配单个字符
   以方括号`[]`包含单个字符的匹配列表；
   以叹号`!`表示不忽略(跟踪)匹配到的文件或目录；

   此外，git 对于 .ignore 配置文件是按行从上到下进行规则匹配的，意味着如果前面的规则匹配的范围更大，则后面的规则将不会生效；