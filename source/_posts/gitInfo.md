---
title: gitInfo
date: 2019-02-20 17:58:18
tags: git
---
1. git reflog 命令获取到的内容为本地仓库所有发生过的变更
1. git branch -m feature/stor-13711 feature/story-13711  修改分支名称
1. git config --global --edit
1. git rm --cached  从git索引和缓存中删除 
2. git mv 重命名或者移动文件
3. git reset --soft "HEAD^" 留下当前变更内容
4. git reset head 从当前缓存区删除
5. git checkout .  撤销当前工作区修改
6. git commit --amend 修改上次提交信息
7. git log --oneline/--raw 
8. checkout只会移动HEAD指针，reset会改变HEAD的引用值。
9. git config --global user.name [user.email]
10. git tag -a 'annotate' -m 'message'
11. git remote set-url --add <name> <newurl>  添加多个url
12. git tag -d <tag-name>  
13. git status --ignored  显示忽略掉文件
14. git checkout --orphan <branch-name>  新建没有commit的分支
1. git push origin :refs/tags/<tag-name>  删除远程tag
2. git branch -u <origin/mybranch> 设置远程分支 
2. git branch -vv 查看本地分之关联情况
2. git checkout -  最近两个分子间切换
1. git commit -m "Big-ass commit" --allow-empty
1. git commit --amend，撤销上一次提交到暂存区，并重新提交内容；
