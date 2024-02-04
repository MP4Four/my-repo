# 撤销修改
git restore a.c
将工作区中的 a.c 恢复至 暂存区的 a.c，a.c 中的内容退回

git restore --staged a.c
将 a.c 移出暂存区，工作区的内容不变，a.c 变为 untracked 状态

# 关联
git remote add origin git@github.com:MP4Four/my-repo.git
origin 就是 git@github.com:MP4Four/my-repo.git 的别名

# 推送
git push -u origin main:main
-u 是 upstream 的缩写
origin 是远程仓库名
main:main 指把本地仓库的 main 分支 推送给远程仓库的 main 分支
如果本地分支名与远程分支名相同，只写成`git push -u origin main`就行了

# 拉取
git pull <远程仓库名> <远程分支名>:<本地分支名>
git pull origin main:main
<=>等价于
git pull
pull 指令会自动合并，如果没有冲突就合并成功，有冲突就需要手动合并

git fetch 会获取远程仓库的修改内容，然后等待我们手动合并
修改了这一行

# 分支
## 查看
git branch

## 新建
git branch dev

## 切换
git checkout dev  (deprecated)
ps: checkout dev，dev有可能是文件也有可能是分支名，如果二者相同，就会有歧义，checkout默认会切换分支，git在 v2.23 版本后添加了新命令 switch 用来专门切换分支

git switch dev

## 合并
git merge dev
dev 为将要被合并的分支，当前所在的分支就是合并后的目标分支