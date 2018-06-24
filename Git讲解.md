# Git的安装
- [下载网站]( https://git-scm.com/)
- 有关git参考资料
> - [git 官方网站](https://git-scm.com/book/zh/v2)
> - [廖雪峰git 学习资料](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)
> - [莫烦Python](https://morvanzhou.github.io/tutorials/others/git/)

# Git基础的配置
- 配置用户名和邮箱样例
```
git config --global user.name "Kojewang"
git config --global user.email "Kojiewang@163.com"

```
- 检查配置的情况
```
git config --global user.name
git config --global user.email
```
> 如果配置的正确将会在命令行下成功显示出你的用户名和邮箱

# Git的基本使用流程
- 新建一个版本控制库
> 在当前的工作目录下，右键使用git bash，输入`git init`，此时当前文件夹下面会多出一个隐藏文件.git隐藏文件夹
- Git基本的使用
    - 新建编辑文件
    - 添加 `git add .`
    - 提交 `git commit -m "***"`
    - 跳过暂存区提交 `git commit -a -m "***"`
    - 移除git中的文件 `git rm **`
    - 查看git中的文件的状态 `git status`
    - git中修改名称 `git mv file_from file_to`
    - git中查看修改的版本历史 `git log ` 其中`-p`参数可以查看每次提交的差异，加上`-2`可以查看最近两次提交的差异
    - 获取github上的资源到本地使用命令
    ``` 
    git clone https://github.com/kejiewang/gitskills.git
    ```
- Git的基本原理
    - 注意在Git管理的文件处于两种状态：已追踪和未跟踪。
        - 已追踪文件分为未修改，已修改和暂时存储
        - 不属于上述的文件为未跟踪文件
        - Git文件生命周期图![image](https://morvanzhou.github.io/static/results/git/2-1-1.png)
        由上面的图可以看到分为四类文件
            - untracked 表示还没有进入追踪的文件
            - unmodified 表示该文件没有进行修改，已经在上次提交的范围里面
            - modified 表示该文件已经进入修改，还没有进入暂存区
            - staged 表示该文件已经进入暂存区还没有进行真正的提交
        
        总结一下：我们可以把这些文件想象成老师布置的作业，modified表示该作业你已经在写了，staged表示你这个作业已经完成了，但只是放进了书包里面，而unmodified表示你已经把作业从书包里面取出来交到了老师的手里了。
        - 如果想要知道某一个文件处于在什么状态下，输入命令`git status` 可以看到以下情况
        ```
        $ git status
            On branch master
            nothing to commit, working directory clean
        ```
        上面表示你现在的文件没有任何的修改距离上次提交记录
        - 追踪新的文件 `git add xxx`其中xxx表示文件名
        

- Git的时间机器
    - 从暂时存储区移除一个文件 `git reset **`
    - ![image](https://morvanzhou.github.io/static/results/git/2-2-1.png)
    - ![image](https://morvanzhou.github.io/static/results/git/2-2-2.png)
    - ![image](https://morvanzhou.github.io/static/results/git/2-2-4.png)
    - 由上图的三种图片可以看到通过HEAD的跳转随时回到之前的任意一个版本
    - 跳转之前的版本 `git reset --hard HEAD` 跳转前面一个
    - `git reset --hard HEAD^`跳转前面两个版本
    - `git reset --hard ***`跳转任意的版本号
    - `git reflog`查看最近使用的版本号，查看HEAD的跳转
- Git的分支管理
> Git是可以进行分支管理的。什么意思呢？比方说一个软件开发你想开发一个新功能但是你没有底气，你怕你增加的这项功能会使之前的工作全泡汤。这时候你就可以使用Git的杀手锏功能分支Branch，之前的版本我们都是在master上面进行开发的。
- `git checkout dev`创建一个dev分支
- `git checkout -b dev`创建并切换到dev分支里面
- `git branch` 查看分支的情况
- `git merge dev` 将分支进行合并，但这样就不会存在commit信息可以采用`git merge --no--f -m "keep message"`的方式进行合并
- GiHub的使用
    - 注册账号
    - 个人中心创建 repository:
        ![img](https://morvanzhou.github.io/static/results/git/5-1-1.png)
    - 按照提示`git push -u origin master`
        ![img](https://morvanzhou.github.io/static/results/git/5-1-2.png)
 
 




