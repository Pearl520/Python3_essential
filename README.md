# Python3_essential
📝 ：记录学习python的一些历程
### 2022年4月11日 第一次提交笔记 删除了
### 2022年4月12日 第二次提交笔记 
#### 原因：在本地更改了名字，导致Git删除了原文件 （Git如果不是用`git mv`,会认为你把文件del了）
##### 解决方法：删除了原来的远程仓库重新建了一个新仓库。
#### 在`git push -u origin main`环节遇到了`error: failed to push some refs to`的报错
##### 解决方法：`git pull --rebase origin main`
##### 问题原因：本地库和远程库的改变没有保持一致，rebase后删除了之前的commit。
###### 学好Git太重要了😭
