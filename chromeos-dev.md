# Setup Chrome OS for Development Mode

## Access debian mount
- Open shell window `ctrl+alt+t`
- Access to shell `shell`
- Access to debian `sudo startcli` or `sudo enter-chroot`

## Setup editor
- First you need to `sudo apt-get update`.
- __git__ install `sudo apt-get install git`.
- __tmux__ install `sudo apt-get install tmux`.
- __vim__ install `sudo apt-get install vim`.
- __vundle__ is __vim__ bundle and plugin manager, to install `git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim`. 

 Then copy below script to __.vimrc__ file and run command `vim +PluginInstall +qall` or launch `vim` and run `:PluginInstall`.

```vim

set nocompatible              " be iMproved, required
filetype off                  " required

" set the runtime path to include Vundle and initialize
set rtp+=~/.vim/bundle/Vundle.vim
call vundle#begin()
" alternatively, pass a path where Vundle should install plugins
"call vundle#begin('~/some/path/here')

" let Vundle manage Vundle, required
Plugin 'VundleVim/Vundle.vim'

" The following are examples of different formats supported.
" Keep Plugin commands between vundle#begin/end.
" plugin on GitHub repo
Plugin 'tpope/vim-fugitive'
" plugin from http://vim-scripts.org/vim/scripts.html
" Plugin 'L9'
" Git plugin not hosted on GitHub
Plugin 'git://git.wincent.com/command-t.git'
" git repos on your local machine (i.e. when working on your own plugin)
Plugin 'file:///home/gmarik/path/to/plugin'
" The sparkup vim script is in a subdirectory of this repo called vim.
" Pass the path to set the runtimepath properly.
Plugin 'rstacruz/sparkup', {'rtp': 'vim/'}
" Install L9 and avoid a Naming conflict if you've already installed a
" different version somewhere else.
" Plugin 'ascenator/L9', {'name': 'newL9'}

" All of your Plugins must be added before the following line
call vundle#end()            " required
filetype plugin indent on    " required
" To ignore plugin indent changes, instead use:
"filetype plugin on
"
" Brief help
" :PluginList       - lists configured plugins
" :PluginInstall    - installs plugins; append `!` to update or just :PluginUpdate
" :PluginSearch foo - searches for foo; append `!` to refresh local cache
" :PluginClean      - confirms removal of unused plugins; append `!` to auto-approve removal
"
" see :h vundle for more details or wiki for FAQ
" Put your non-Plugin stuff after this line
```
 
- __zsh__ to install `sudo apt-get install zsh`.

- __OhMyZsh__ to install via __wget__ `sh -c "$(wget https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O -)"`.


## Github GPG Sign-in

- Create new gpg key `gpg --gen-key`.
- Show key list `gpg --list-secret-keys --keyid-format LONG`.
- Export key `gpg --armor --export [KEY_ID]` and copy to github.
- Open github and add new GPG key with copied key.
- Read more about this [link](https://help.github.com/articles/generating-a-new-gpg-key)
