# 查看创建的分支,按时间倒序排列

## 远程分支
for branch in `git branch -r | grep -v HEAD`;do echo -e `git show --format="%ci %cr" $branch | head -n 1` \\t$branch; done | sort -r | more

## 本地分支
for branch in `git branch|perl -pe s/^..//`;do echo -e  `git show --format="%ci %cr" $branch | head -n 1` \\t$branch; done | sort -r | more