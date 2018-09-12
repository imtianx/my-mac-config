
# Install Softwares


## 1.[brew](https://brew.sh/) 安装低版本软件

以 安装 `python` 为例。由于 mac默认安装有 python2 ,为了不覆盖 python2 ,这里安装 python3 ，并且所有的 命令都带 `3` 以区别。

如果目前 python 最新为 `3.7.0`, 但是由于某些软件的兼容性，需要 `3.6.x` 版本 直接用下面的命令 安装的都是最新的。

```
brew install python3
```

**这里，通过在 [Formula](https://github.com/Homebrew/homebrew-core/blob/master/Formula/) 中找到 相关软件的 rb文件的指定版本,在本地切换到相应的版本，然后进行安装。**


这里通过 查看 `python.rb` 文件的提交日志，找到需要安装的 3.6.5 版本的 commit id :  f2a764ef9

然后终端 进入本地的 Formula 目录，切换分支，安装软件，最后再切回到master:

```
cd /usr/local/Homebrew/Library/Taps/homebrew/homebrew-core/Formula

git checkout f2a764ef9

// 注意这里 要用 python ，不能用 python3，否则安装仍是最新版本软件
brew install python

git checkout master

```
进入目录中，可以查看 python.rb 文件，通过 url 处的连接查看软件的版本。


由于 brew 每次安装软件前都会检查更新，可以关闭 ：

```
export HOMEBREW_NO_AUTO_UPDATE=true
```




