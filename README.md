# clean-dotfile

总结了一下自己使用linux以来经常使用的一些custom configation, 结合网上的[awesome dotfile](https://github.com/webpro/awesome-dotfiles),建了此 repo,以便更换开发环境时随时all-in。

主要包括系统dotfile(位于system目录下),vim dotfile(位于vim目录下)，tmux dotfile(位于tmux目录下)。

各dotfile使用以及说明如下：

## system dotfile

#### 使用

```bash
$ git clone https://github.com/zhangchenchen/clean-dotfile.git ~/.dotfiles

$ source ~/.dotfiles/system/.bash_profile
```

如果想长期生效的话（重启后仍可用），可以将这些system dotfile 覆盖到根目录下，不过建议使用软连接的方式，如下：

```bash
$ ln -sbv ~/.dotfiles/system/.bash_profile ~

$ ln -sbv ~/.dotfiles/system/.inputrc ~
```

#### 说明

简单说下各文件的作用（详细说明见注释）：

- .bash_profile:最先读取，搜索 system目录下的dotfile并activate(做source操作)。
- .alias: 顾名思义，就是重新定义了一些使用频率比较高的命令。![alias](http://7xrnwq.com1.z0.glb.clouddn.com/2017-06-08alias.png)
- .inputrc: 键盘布局，直接引用[inputrc](https://github.com/webpro/dotfiles/blob/master/runcom/.inputrc)
- .env: 环境变量配置。
- .func: 一些自定义函数，比如 mkd test 会创建 test目录并进入该目录。
- .prompt: prompt设置。生效后效果如![prompt](http://7xrnwq.com1.z0.glb.clouddn.com/2016-06-08prompt1.png)


## vim dotfile



## tmux dotfile


