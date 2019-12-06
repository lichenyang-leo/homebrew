# homebrew
相关命令

## 什么是 Homebrew 与 Homebrew Cask

### 相当于macos包管理

Homebrew 是基于 OS X 的套件管理工具，是一个开源的 Ruby 脚本，专门用于快速下载软件。更通俗地讲，Homebrew 类似于一个软件中心，你可以理解成 App Store 或者 Google Play 那样的软件商店，只不过，Homebrew 比前者以及 Mac App Store 来说有着更丰富的资源与更高效的管理，具体会在下文提及。

至于 Homebrew Cask，它是一套建立在 Homebrew 基础之上的 OS X 软件安装命令行工具，是 Homebrew 的扩展。不拿那么多拗口的术语来烦你了，简言之，你完全可以把 Homebrew Cask 当作是 Homebrew 的一部分，你只需要记住，在安装常用软件的过程中，大部分情况下我们只需要使用 Homebrew Cask 就足够了。

---

## 优势
---

- 通过 Homebrew 下载安装的软件全部来自对应的软件官网，无需担心下载源的安全问题。

- 依存于系统既有的库，减少了空间占用和冗余

-安装软件 / 软件包 / 软件都在一个目录下，方便管理，这也是 Homebrew 能如此受欢迎的最大原因之一

Homebrew Cask 的常用命令非常简单，也很好理解，虽然是通过命令行，但你完全不需要对「终端」「命令行」有过多了解，也能很快上手。

不管是 Homebrew 还是 Homebrew Cask，它们除了安装软件外还能帮你做一些其他操作，因此，你花费一定的学习成本带来的效率提升，是值得的。

## 下载的软件路径

会从官网下载最新，无需担心安全问题，下载在统一路径  /usr/local ，图形化的软件在Caskroom下，其余在Cellar下

## 常用命令
安装homebrew : /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
如果有错误提示，可在终端中执行 xcode-select --install，在弹出的窗口选择 Install 以安装 Command Line Tools，路径为 /Library/Developer/CommandLineTools，如要卸载，删除此文件夹即可。当然也可以到 Mac App Store 安装体积庞大的 Xcode。

---

## Homebrew Cask 原理
之前，是用软链接的方式将应用链接到 Application 文件夹，有人说这样的方式会导致 Spotlight 无法检索到。但现在，它是将应用直接移动到 Application 文件夹，这与我们自己去官网下载应用再安装是完全一致的，后续更新或卸载也按平常的方式即可。

当然，也可以用 brew cask uninstall 应用名称 的方式，这种方式才会删除路径 /usr/local/Caskroom 中保留的应用信息文件，这样当我们用命令 brew cask list 查询已安装列表时，已卸载的应用才不会仍显示。也就是说，如果按照平常的方式，比如直接移到废纸篓，那么还需手动删除 Caskroom 中的应用信息文件。当然，不删除也没啥影响，因为一般没必要查看已安装列表，已安装应用在 Launchpad 中查看就好。

下载命令： brew cask install <文件名> 

卸载软件： brew cask uninstall <文件名> 

搜索可以安装的软件： brew cask search 列出所有可以被安装的软件，当然你也可以直接前往 Homebrew Cask 搜索
eg: brew cask search google : google是关键词，可以模糊查询

查找相关软件信息： brew cask info <软件名>

删除homebrew 下载的软件： brew cask cleanup

列出通过homebrew下载的包： brew cask list 

更新homebrew cask : brew cask update



