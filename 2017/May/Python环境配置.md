####小说Python开发环境配置

Python是一门简单、容易上手的脚本语言。同时也有着众多的发行版本。在开发不同程序的时候往往也要用到不同的package，不同的包与兼容性问题。今天我们就来一次性解决这些对于新手来说稍显繁琐的内容。

#####新手的问题
新手最常问的问题是什么？在我看来新手最大的问题是选择困难症。从开发工具到语言选择，从学习方向到基础知识，最后容易迷失在苍茫码海之中。 我们都知道上山的路定然不止一条，每个人都有自己的出发点，但是出发之前要做的准备都是差不多的啦。

所以这里给出一套简要的、够用的、基于Mac解决方案。简要的是说，这套方案需要的东西不多，你不需要了解太多的内容。够用的是说，在你进一步去学习实践更多的内容之前，这套方案是够用的，并且有着足够的拓展性。

#####编辑器
编辑器就是你写代码的工具，你当然可以用自带的编辑器来输入，也可以选择一个完整的IDE。但是作为一个高段位工具，IDE会帮你太多。会给你太多的提示，对于想要建立思维的新手来说，个人认为IDE并不是最好选择。你当然也可以选择VIM 或者Emacs 这样的全能型编辑器，但是这两个的学习成本也是你需要考虑的问题。我也不太会用也是另外的一个重要原因。

这里推荐使用[Sublime Text 3][1]。Sublime text 3 有着众多的第三方插件可以选择，并通过[Package control][2] 来方便的安装，这可以大大的节约你未来的开发成本。当然，一开始的时候我们并不需要安装什么插件也可以。但至少你可以通过Package Control 来安装一个好看的主题，赏心悦目一下。你可以选择不购买Sulime 的正版授权，代价无非就是会经常提醒你去买一个授权而已。 有能力还是支持一下最好，毕竟开发是需要成本的。

#####Python版本切换
前文说到，Python 有着众多的发行版，不同的版本支持不同的插件，比如MySql 数据库支持的Python Connector 就要求必须是Python 3.3以上的版本，但是你同时完全可能需要一些2.7 版本的Python 来完成一些工作。

Mac 本身自带的是Python2.7 的版本，这个版本最好不要去动它，毕竟涉及到很多操作系统的操作，和一些兼容性问题，会带来很多的麻烦。 你当然可以选择通过官方的途径来安装Python，然后从命令行通过`python3` 的命令来启动对应的Python 解释器。但是既然有方便好用的插件为什么不来试试呢？

这里推荐的是[PyEnv][3] Mac的操作系统中有一个名为PATH 的环境变量。你可以理解为一本黄页，当你在命令行中输入大部分命令的时候操作系统会去这个“黄页”中寻找对应名称的应用程序并启动。PyEnv就是在这个PATH 中插入了一本小书，这样有需要的时候就可以通过管理这本小书来管理Python的不同版本了。
官网推荐使用[HomeBrew][6] 来进行安装。先安装HomeBrew 然后再安装PyEnv 就好了，很简单。如果已经安装过HomeBrew 记得先升级HomeBrew 再安装。这里说说可能遇到的一个小问题，其他的安装说明去看看就好了。

Q:`zipimport.ZipImportError: can't decompress data; zlib not available`
A:一开始我以为这个问题是缺少zlib，所以通过homebrew 安装了zlib 但是它提示我说mac 系统已经自带了zlib 重复安装可能会造成问题，还要修改相关的一些设定。 一看就很麻烦的样子，从GitHub上发现外国友人也有这个问题，通过`xcode-select --install` 问题解决。

安装完PyEnv 之后可以通过`pyenv install --list` 获取可安装的Python版本列表安装即可。你也可以通过`pyenv versions` 来查看已经安装过什么版本。需要注意的是，之前如果通过其他的渠道安装过Python 的不同版本，并不会出现在随后的列表当中，也就不能方便的实现不同版本之间的切换，这也是我一开始就推荐使用pyenv 来管理不同版本Python 的原因。

#####Python virtualEnv
virtualEnv 是一款配置不同Python 开发虚拟环境的插件。你可以通过它来安装不同的package。但是pyenv 为我们提供了一个更佳方便的插件 [pyenv-virtualenv][4]。啥也不说了，去按照官网的提示安装就好了。 同样是使用HomeBrew 安装。

在你的~/.bash_profile 文件中添加如下两行。
```
eval "$(pyenv init -)"  
eval "$(pyenv virtualenv-init -)"
```
接下来就是使用pyenv-virtualenv插件来配置虚拟开发环境了。
你只要在shell 中运行`pyenv virtualenv <python-version> <virtualenv-name>`就可以建立自己的全新虚拟环境。

输入`pyenv activate <virtualenv-name>`就可以激活对应的虚拟环境了。

####总结
sublime text 3 + pyenv + pyenv-virtualenv = “简单、够用的python开发学习环境”。

当然你最好使用的是Mac，并且安装好了[科学上网]插件，和HomeBrew。 如果有其他疑问欢迎留言讨论，不保证即时性，但是都会看到回复的。



[1]:https://www.sublimetext.com/
[2]:https://packagecontrol.io/
[3]:https://github.com/pyenv/pyenv
[4]:https://github.com/pyenv/pyenv-virtualenv
[5]:http://joinyt.com/?r=929656e3e08dd181
[6]:https://brew.sh/