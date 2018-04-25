## 最佳实践

[GIT使用规范流程](http://www.ruanyifeng.com/blog/2015/08/git-use-process.html)

[GIT分支管理策略](http://www.ruanyifeng.com/blog/2012/07/git.html)



**GIT项目管理**

- 统一`分支`在远程服务器定义
- 统一`tag`在远程服务器定义
- 保持项目的`分支`名称本地和远程统一，并且有联系关系



### 分支管理



#### 一、主分支Master

默认项目应该只有一个`Master` 主分支，这个分支为用户使用的正式版本，尽量`tag`在主分支上打。



#### 二、开发分支develop

日常开发的主要分支，完成某些重要的功能可以合并到主分支。



### 三、功能分支 feature

多人开发项目的时候，可以按照功能开发，`feature-x`等多条功能分支，合并为`develop`分支。

**开发完功能后，最好删除分支，保持项目分支的整洁**



### 四、修补bug分支

通常在正式版`Master`分支难免有`bug`，所以要在`Master`分支分离出一个修补的分支`fixbug-x`。

修补后，要合并`Master`主分支和`develop`分支，并且删除`fixbug-x`分支。

