####pyenv + virtualenv install

python 有着众多的发型版本，有人推荐使用Anaconda 管理相关包，我还不太会用，就采用了其他方式。
#####名词解释
+ [virtualenv][2]可以提供一个虚拟的python 运行环境。
+ [pyenv][3] 提供多版本Python 之间的切换功能。
+ pip Python 自带的包管理工具。
+ package 包 简单理解成一套已经成型的工具，或者说原料，可以帮助你更快的开发python 应用
+ [pyenv-virtualenv][4] pyenv 的一个插件，可以帮助方便的建立virtualenv 运行环境。

一开始学习的时候我从[Python官网][1]下载了pkg 的安装包，一直使用的都是3.5.2版本，官网的安装包还包括了IDLE 和PythonLauncher等组件。但是我一直都没有怎么使用，从廖老师的教程中学习了从命令行启动Python 的方式。 我使用Mac 自带一个2.7.10 的Python 版本，如果直接从命令行输入`python`，就可以启动这个版本。想要启动Python3 在命令行输入`python3` 即可。

安装VirtualEnv 

命令行直接输入`pip install virtualenv` 即可。

安装pyenv
从Homebrew 安装。`brew install pyenv` 即可。

理解pyenv
pyenv 的原理大概修改python 对应的一个路径 ~/.bash_profile 文件中有一个PATH 变量，当你在命令行输入命令的时候，shell 会根据这个文件按照从下到上，从左到右的顺序去搜索对应的文件名打开相应的文件。pyenv 会在这个变量中增加一个shim 文件夹，并管理其中的内容，从而实现python版本的切换。
`pyenv versions` 会显示已经安装的python 版本。但是一开始只会显示一个system 的版本，这是由于，从官网下载的python 并没有安装在pyenv 都应的管理文件夹下面。 你需要通过`pyenv install --list` 获取可安装的版本列表，重新安装才行。

安装过程中遇到的问题
Q:`zipimport.ZipImportError: can't decompress data; zlib not available`
A:一开始我以为这个问题是缺少zlib，所以通过homebrew 安装了zlib 但是它提示我说mac 系统已经自带了zlib 重复安装可能会造成问题，还要修改相关的一些设定。 一看就很麻烦的样子，从GitHub上发现外国友人也有这个问题，通过`xcode-select --install` 问题解决。

其他的内容大都从github 主页可以找到答案，需要注意的是需要修改`~/.bash_profile` 文件。输入`$ echo 'eval "$(pyenv init -)"' >> ~/.bash_profile` 这条命令会在`~/.bash_profile`文件中添加一行`eval "$(pyenv init -)"`，你也可以用其他编辑器打开这个文件之后修改保存即可。

pyenv-virtualenv `brew install pyenv-virtualenv` 即可安装成功，需要在`~/.bash_profile`中再添加一行`eval "$(pyenv virtualenv-init -)"`现在可以使用pyenv 配合 pyenv-virtual 方便的切换python版本和对应的运行环境了。

例如
`pyenv virtualenv <venvname>` 可以从当前运行的python 创建一个虚拟环境。
`pyenv activate <venvname>` 可以激活`venvname`这个虚拟环境，之后可以在其中使用pip 安装相应的python 包。 个人感觉直接激活一个包要比用virtualenv 去激活一个路径方便多了。 而且一个虚拟环境可以在多个项目中应用，这点也要比virtualenv 更加方便。

开始你的python 之旅吧。
[1]:https://www.python.org/
[2]:https://virtualenv.pypa.io/en/stable/
[3]:https://github.com/pyenv/pyenv
[4]:https://github.com/pyenv/pyenv-virtualenv