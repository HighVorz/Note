#### 仓库
```bash
# 创建仓库
git init	# 当前目录作为仓库
git init <repository> # 指定目录作为仓库
```

```bash
# 克隆仓库
git clone <repo> # 在当前目录下创建一个仓库, 即项目文件夹
git clone <repo> <directory>	# 指定目录创建仓库
git clone <repo> <new_name> # 修改克隆名称
```

#### 账号信息

``` bash
git config --global user.name "runoob"
git config --global user.email test@runoob.com
git config --global --list 
```

#### 修改commit信息
``` bash
git commit --amend 
```

#### 回退
``` bash
git reset --soft HEAD^ 回退上一commit, 并保留更改
git reset --hard HEAD^ 回退上一commit, 并丢弃更改
```

#### 推送并设置上游分支
``` bash
git push -u
```

#### 工作区
``` bash
git work list
git worktree add <path> <branch-name>  # 分支不存在将创建
git worktree remove
```


#### 分支

```bash
# 创建分支
git branch <branch>
git branch # 当前分支
git branch -a # 所有分支
git checkout -b <branch> # 创建并切换分支
git checkout <hash>
```

```bash
# 删除分支
git branch -d <branch-name>
git branch -D <branch-name>
```

``` bash
# 查找最早分支
git log --reverse --date-order
```

#### 提交
``` bash
# ssh免密提交
git remote set-url origin git@gitee.com:HighVorz/app.git (新地址)
```

#### 删除
``` git
git rm -r --cached + 想要删除的文件夹
```

#### 跟踪
``` bash
# 删除readme1.txt的跟踪，并保留在本地。
git rm --cached readme1.txt    
# 删除readme1.txt的跟踪，并且删除本地文件。
git rm --f readme1.txt    

# 删除文件夹下跟踪
git rm -r dir/*

# 列出跟踪文件
git ls-files
```

#### 历史
```bash
git log
git log -p <file> //查看指定文件的提交历史
git blame <file> //列表形式查看
```

#### 撤销

```bash
git reset --hard HEAD //撤销所有未提交文件的修改内容
git checkout HEAD <file> //指定文件撤销
git revert <commit> //撤销指定提交
```




#### 标签

```bash
git tag	//列出所有本地标签
git tag <tagname> //最新提交创建标签
git tag -d <tagname> //删除标签
```

#### 合并分支

```cpp
git merge <branch> //合并指定分支到当前分支
```

#### 本地覆盖远程&&远程覆盖本地

``` bash
git push origin master --force

git fetch --all
git reset --hard origin/master
git pull origin master

```

#### 衍合(忽略)

从主分支分出当前分支, 主分支发生更新, 当前分支需要合并最新主分支

```bash
git rebase <branch> 
```



#### 远程仓库



**添加远程仓库**

``` git
git remote add origin <url>
```



**修改远程仓库**

🚀

``` bash
git remote set-url origin https://gitee.com/xx/xx.git (新地址)
```



**信息**

```bash
git remote -v	 //查看远程版本库信息
git remote show <remote> //查看指定远程版本库信息
git remote add <remove> <url> //添加远程版本库
git fetch <remove> //从远程版本库获取代码
git pull <remote> <branch> //下载代码并合并
git push <remote> <branch> //上传代码并合并
git push --tags //上传所有标签
```



#### 子模块

`.gitmodule`文件中描述了项目依赖的子git项目模块

``` yaml
[submodule "third_party/pixman"]
path = third_party/pixman
url = https://github.com/aseprite/pixman.git
```



``` bash
git submodule update --init --recursive # 获取依赖的子模块
```

#### 暂存

``` bash
git add filename 添加文件到暂存区。
git add .        添加全部文件

git commit -m "注释" 将暂存区内容添加到仓库中
git reset --hard HEAD^   回退上一版本^ 或者版本号
git reflog 操作日志

# 丢弃
git checkout -- filename 
git checkout .  丢弃全部
```

#### 差异比较
``` bash
git diff HEAD  -- filename
```