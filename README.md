总结了一下自己使用linux以来经常使用的一些custom configuration, 结合网上的[awesome dotfile](https://github.com/webpro/awesome-dotfiles),建了此 repo,以便更换开发环境时随时all-in。

主要包括系统dotfile(位于system目录下),vim dotfile(位于vim目录下)，tmux dotfile(位于tmux目录下)。

各dotfile使用以及说明如下：

## 一， system dotfile

#### 1.1使用

```bash
$ git clone https://github.com/zhangchenchen/clean-dotfile.git ~/.dotfiles

$ source ~/.dotfiles/system/.bash_profile
```

如果想长期生效的话（重连后仍可用），可以将这些system dotfile 覆盖到根目录下，不过建议使用软连接的方式，如下：

```bash
$ ln -sbv ~/.dotfiles/system/.bash_profile ~

$ ln -sbv ~/.dotfiles/system/.inputrc ~
```

#### 1.2说明

简单说下各文件的作用（详细说明见注释）：

- .bash_profile:最先读取，搜索 system目录下的dotfile并activate(做source操作)。
- .alias: 顾名思义，就是重新定义了一些使用频率比较高的命令。![alias](http://7xrnwq.com1.z0.glb.clouddn.com/2017-06-08alias.png)
- .inputrc: 键盘布局，直接引用[inputrc](https://github.com/webpro/dotfiles/blob/master/runcom/.inputrc)
- .env: 环境变量配置。
- .func: 一些自定义函数，比如 mkd test 会创建 test目录并进入该目录。
- .prompt: prompt设置,生效后效果如下：

   ![prompt](http://7xrnwq.com1.z0.glb.clouddn.com/2016-06-08prompt1.png)


## 二，vim dotfile

本来是想把这个[repo](https://github.com/amix/vimrc)拉过来做submodule，看了一下，感觉内容还是太多。就分了两个版本，一个basic-version，就是上述repo中的basic-version。自己加了一个plugin-version，添加了一些自己常用的插件。

#### 2.1使用

- basic-version使用比较简单，直接将该目录下的[.vimrc](https://github.com/zhangchenchen/clean-dotfile/blob/master/vim/basic-version/.vimrc)覆盖（或软链接）根目录下.vimrc。
- plugin-version版本，首先安装插件管理vundle，然后配置并安装插件。

```bash
$ git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim
```

然后将该目录下的[.vimrc](https://github.com/zhangchenchen/clean-dotfile/blob/master/vim/plugin-version/.vimrc)覆盖（或软链接）根目录下.vimrc。

因为 插件Tagbar依赖ctag包，这里可能还需要安装ctag.

```bash
$ yum upgrade -y 
$ yum install ctags.x86_64 # for ubuntu use 'apt-get install exuberant-ctags'
```

安装插件：

```bash
$ vim +PluginInstall +qall
```


#### 2.2说明

- basic-version: vim的基本配置（比如显示行号，显示状态号等），以及自定义的快捷键（文件保存等）。
- plugin-version：插件包括项目浏览[Nerdtree](https://github.com/scrooloose/nerdtree),文件模糊查询[CtrlP](https://github.com/kien/ctrlp.vim),代码补全 [YouCompleteMe](https://github.com/Valloric/YouCompleteMe),语法检查 [Syntastic](https://github.com/vim-syntastic/syntastic),tag窗口[TagBar](https://github.com/majutsushi/tagbar)。几张截图如下：


![nredtree](http://7xrnwq.com1.z0.glb.clouddn.com/2017-06-08nerdtree.png)

![tagbar](http://7xrnwq.com1.z0.glb.clouddn.com/2017-06-08tagbar.png)


## 三，tmux dotfile

####3.1 使用

安装tmux后，将tmux目录下的[.tmux.conf](https://github.com/zhangchenchen/clean-dotfile/blob/master/tmux/tmux.conf) 覆盖（或软链接）根目录下.tmux.conf。
注：RH系类需要覆盖（或软链接）/etc/tmux.conf


####3.2 说明

改动比较小

- 将水平/垂直新建pane改为 “-” 和 “\”
- 把hjkl设置为切换窗格的快捷键
- 更改配置文件后 Ctrl+r 可以直接reload