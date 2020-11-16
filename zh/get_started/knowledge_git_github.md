git 和 github 介绍
=====

因为在学习 MaixPy 的过程中， 有很多地方用到 git 和 github， 所以这里简单解释一下它们是什么，以及区别是什么。


## 什么是 git

git 是一款 代码托管 **软件**， 用来管理代码的版本。
比如：
我今天改了代码， 然后明天也改了代码， 以后我都能看到这两次改动历史， 以及改了什么内容，可以精确到哪一行，方便后面找问题;
或者我发现第二次提交的代码出现了问题， 我需要回到第一次提交后的版本， 都可以用这个工具实现;
另外方便多个人修改同一份代码，能管理大家提交的代码，不容易出现混乱。

再也不用拷贝无数个文件夹来备份修改了！

git 会在目录下创建一个`.git`隐藏文件夹， 所有更改记录保存在这里面，不能删除这个文件夹。

但是需要注意的是， 现在的 git 主要用来管理文本文件， 不适用拿来管理二进制文件，比如图片 PDF等等， 会让文件夹占用的空间变得很大。

具体的教程，可以看 [这里](https://git-scm.com/), 中文教程可以看 [这里](https://www.liaoxuefeng.com/wiki/896043488029600/896067008724000)


## 什么是 github

[github](http://github.com/) 是一个 分享代码 的 **网站**。

可以在这个网站上注册， 然后建立仓库（repository），往这个仓库里面放代码公开分享，让更多地人来使用， 甚至一起修改，一起优化代码， 这就是**开源**。

每个仓库都是可以单独地使用 `git` 这个软件来管理的， 大家在自己的电脑上修改代码， 然后使用`git`提交， 然后使用`git`推送到`github`这个网站， 大家就可以看到新的内容了。

MaixPy 的源码的地址是： [https://github.com/sipeed/maixpy](https://github.com/sipeed/maixpy) , 也就是一个 `git 仓库`。


github 的[帮助](https://docs.github.com/en/free-pro-team@latest/github), 中文 [帮助](https://docs.github.com/cn/free-pro-team@latest/github)

## git 和 github 的区别

一个是一个软件， 一个是一个网站。
只不过这个网站用到了 git 这个技术来管理仓库。

## 什么是 star

在 github 上， 每个公开的仓库大家都可以去点赞收藏，也就是 star，在 github 右上角 ⭐ 形状的按钮
![](/assets/other/github_star.jpg)
如果你觉得项目不错，请给个 star，这样会鼓励开发者花更多时间维护仓库，同时也告诉第一次来的访问者这是个不错的项目，值得关注。

star 后， 可以在个人资料里面找到自己的 star 仓库，方便下一次找到

说到这里，大家觉得 [MaixPy](https://github.com/sipeed/maixpy) 不错的话，可以 star 一个哦～

## 什么是 Master 分支

在每个仓库中， 可以存在很多个分支，不同分支可以有不同的代码，而且不同的分支之间还可以互相合并，方便保存代码的不同版本，以及方便团队合作， master 分支就是指主分支，也就是最重要的分支，通常仓库默认展示的就是 master 分支。


## 什么是 issue

也就是问题的意思， 在github 上， 每个仓库有一个专门用来提问的地方， 比如 [MaixPy的issue](https://github.com/sipeed/MaixPy/issues)
大家在这里提问， 类似论坛一样， 都会被记录下来，方便后面的人查阅

## 什么是 fork

在 github 上， 仓库页面右上角有一个 fork 按钮
![](/assets/other/github_star.jpg)
点击可以将仓库 fork 到自己的仓库，就相当于是一份拷贝，叫 fork 的原因是你在 fork 成自己的仓库后，可以对自己这个仓库进行随意修改，算是原来被 fork 仓库的一个发展分支，源自它但是可以不与它相同


## 什么是 PR

即 github 上的 pull request 功能， 就是参与一个仓库的代码更新， 就是先 fork 成自己的仓库，然后修改，修改后提交合并到被 fork 的源仓库， 具体方法可自行学习



