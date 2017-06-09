a set of dotfile, including bash vim tmux etc. keep simple & clean.

## 1 system dotfile

#### 1.1 use

```bash
$ git clone https://github.com/zhangchenchen/clean-dotfile.git ~/.dotfiles

$ source ~/.dotfiles/system/.bash_profile
```

u may want to overwrite the source file to make it activate everytime.
Highly recommend making a soft link like this:  

```bash
$ ln -sbv ~/.dotfiles/system/.bash_profile ~

$ ln -sbv ~/.dotfiles/system/.inputrc ~
```

#### 1.2 instruction

- .bash_profile:load first, search other dotfile and activate.
- .alias: as the word says.![alias](http://7xrnwq.com1.z0.glb.clouddn.com/2017-06-08alias.png)
- .inputrc: keyboard mappin,copied from[inputrc](https://github.com/webpro/dotfiles/blob/master/runcom/.inputrc)
- .env: environment settings
- .func: Commands that are too complex for an alias are defined in a function，like 'mkd test' will make a test direction and cd into it。
- .prompt: prompt setting,like this：

   ![prompt](http://7xrnwq.com1.z0.glb.clouddn.com/2016-06-08prompt1.png)


## 2 vim dotfile

I was thinking make a submodule with this [repo](https://github.com/amix/vimrc) first, but there were too much complicated things。So, divide into two versions,basic-version just like basic-version from this [repo](https://github.com/amix/vimrc), i added a plugin-version which installed several frequentldy used plugins. 

#### 2.1 use

- basic-version: easy to use. 

```bash
$ ln -sbv ~/.dotfiles/vim/basic-version/.vimrc ~
```

- plugin-version:

first,install [Vundle](https://github.com/VundleVim/Vundle.vim.git), a plugin manager for vim .

```bash
$ git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim
```

make a soft link:

```bash
ln -sbv ~/.dotfiles/vim/plugin-version/.vimrc ~
```

as the 'Tagbar' plugin relies on ctags library, install ctags before install plugins.

```bash
$ yum upgrade -y 
$ yum install ctags # for ubuntu use 'apt-get install exuberant-ctags'
```

install plugins：

```bash
$ vim +PluginInstall +qall
```


#### 2.2 instruction

- basic-version: basic settings of vim, like display line number, display status etc, some shorcut,like save file fast
- plugin-version：plugins include[Nerdtree](https://github.com/scrooloose/nerdtree), [CtrlP](https://github.com/kien/ctrlp.vim), [YouCompleteMe](https://github.com/Valloric/YouCompleteMe), [Syntastic](https://github.com/vim-syntastic/syntastic), [TagBar](https://github.com/majutsushi/tagbar)。some screenshot as follow：

![nredtree](http://7xrnwq.com1.z0.glb.clouddn.com/2017-06-08nerdtree.png)

![tagbar](http://7xrnwq.com1.z0.glb.clouddn.com/2017-06-08tagbar.png)


## 3 tmux dotfile

#### 3.1 use

just make a soft link:

```bash
ln -sbv ~/.dotfiles/tmux/.tmux.conf ~
```

note：RedHat or Centos sysytem may link to /etc/tmux.conf

```bash
ln -sbv ~/.dotfiles/tmux/.tmux.conf /etc/tmux.conf
```


#### 3.2 instruction

a little changing(more details in the comment)

- Split windows with '-' or '\'
- act like vim with binding 'hjkl' 
- 'Ctrl+r' directly reload without source