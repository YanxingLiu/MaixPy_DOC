Documentation Of MaixPy
===========


|[Read me online](https://maixpy.sipeed.com/en/)  | [在线阅读](https://maixpy.sipeed.com/zh/) |
| ------------------------ | ----------- |

[![Build Status](https://travis-ci.org/sipeed/MaixPy_DOC.svg?branch=master)](https://travis-ci.org/sipeed/MaixPy_DOC)


> In addition to [https://maixpy.sipeed.com](https://maixpy.sipeed.com), you can also visit [https://en.maixpy.sipeed.com](https://en.maixpy.sipeed.com). The former is synchronized with the latter's (en) pages, so there is a delay in refreshing the former's pages after document changes, usually less than 3 days.
> 
> Alternatively, if the above page is not accessible, you can also try [https://cn.maixpy.sipeed.com/](https://cn.maixpy.sipeed.com/).




> 除了[https://maixpy.sipeed.com](https://maixpy.sipeed.com) , 您也可以访问 [https://cn.maixpy.sipeed.com](https://cn.maixpy.sipeed.com)  ， 前者是同步的后者（cn）的页面，所以文档修改后前者页面刷新会有延迟，一般小于 3 天
> 
> 另外， 以上页面如果无法访问， 也可以尝试访问[https://en.maixpy.sipeed.com/](https://en.maixpy.sipeed.com/)

## Usage

* `git clone https://github.com/sipeed/MaixPy_DOC.git`
* Just change `.md` file, and document's side bar is `SUMMARY.md`
* If you want to see rendered document page, see below `Build Doc`, or just ignore this step
   but it's recommended to preview check format error before you commit
* Commit changes by `git add -A && git commit -m "udpate doc: your comment"`
* Push to github by `git push origin master`
* All thing is done, just wait page update, you can see build progress [here](https://travis-ci.org/github/sipeed/MaixPy_DOC), you can see your changes on [maixpy.sipeed.com](https://maixpy.sipeed.com) once build is passed



-----------------------------------------------------------------------

## Build Doc(preview locally)

There's two ways to preview locally:

### 1. Use docker(recommend)

* First install docker

* Then:

```
docker build -t gitbook .
docker run -it -p 4000:4000 --network host -v $(pwd):/gitbook --name book0 gitbook /bin/bash
cd /gitbook
gitbook install
./serve.sh
```
next time start by:
```
docker start book0
docker attatch book0
./serve.sh
```
stop by:
```
docker stop book0
```

* Finally visit http://localhost:4000


### 2. Download gitbook-cli to build

This documentation site is powered by GitBook. You can check out the online version here.

You need Node.js and npm to be able to build the site.

To install gitbook:

```
npm install gitbook-cli -g
```

Get Doc source code:
```
sudo apt install git 
git clone https://github.com/sipeed/MaixPy_DOC.git
```

Install gitbook plugins:

```
cd MaixPy_DOC
gitbook install
```

Serve as a website:

```
chmod +x serve.sh
./serve.sh
```

Then visit http://localhost:4000

## Contribution

* fork to your repository
* update doc and commit in your repository
* create a new pull request(PR) and describe what you update in detail. PR help see [here](https://docs.github.com/en/free-pro-team@latest/github/collaborating-with-issues-and-pull-requests/creating-a-pull-request-from-a-fork), [创建合并请求中文教程](https://docs.github.com/cn/free-pro-team@latest/github/collaborating-with-issues-and-pull-requests/creating-a-pull-request-from-a-fork)


