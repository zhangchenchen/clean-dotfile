# clean-dotfile

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
$ ln -sv “~/.dotfiles/system/.bash_profile” ~

$ ln -sv “~/.dotfiles/system/.inputrc” ~
```

### 说明





## vim dotfile


## tmux dotfile


