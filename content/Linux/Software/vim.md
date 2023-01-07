---
title: Vim: Extendable Text Editor
weight: -20
---

### Cut/Copy Paste Registers not working
- \-- set clipboard+=unnamed
- ++ set clipboard=unnamed

### Decrypt gnupg encrypted documents
- Vundle: jamessan/vim-gnupg
- Direct: https://github.com/jamessan/vim-gnupg
- Treat like a normal document
    ```
    vim example.txt.gpg
    ```
    - enter password
    ```
    vim ~/.{bas,zs,fis}hrc
    ```
        ++ GPG_TTY=$(tty)
        ++ export GPG_TTY

### Turn [OFF] Auto Backup
```
vim ~/.vimrc
```
- set nobackup
- set nowritebackup

### Spellcheck
- :set spell spelllang=en_us
- Movement
    - ]s = Next misspelled word
    - [s = Prev misspelled word
- Suggestions
    - z=
- Add to dictionary
    - zg
- Mark for later
    - zw
- turn off with :set nospell

### Vundle
```
git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim
```
- If cp ~/.vim then load vim and run: :PluginUpdate
```
vim ~/.vimrc
```
```    
set nocompatible                  "Switch off later if needed
filetype off                      "^same
set rtp+=~/.vim/bundle/Vundle.vim
call vundle#begin()
Plugin 'VundleVim/Vundle.vim'
Plugin 'ctrlpvim/ctrlp.vim'
Plugin 'preservim/nerdtree'
Plugin 'Yggdroot/indentline'
Plugin 'vim-syntastic/syntastic'
Plugin 'vim-airline/vim-airline'
Plugin 'lervag/vimtex'
Plugin 'xuhdev/SingleCompile'
Plugin 'godlygeek/tabular'
Plugin 'henrik/vim-indexed-search'
Plugin 'vim-airline/vim-airline-themes'
Plugin 'rafi/awesome-vim-colorschemes'
call vundle#end()
filetype plugin indent on
" Brief help
" :PluginList       - lists configured plugins
" :PluginInstall    - installs plugins; append `!` to update or just :PluginUpdate
" :PluginSearch foo - searches for foo; append `!` to refresh local cache
" :PluginClean      - confirms removal of unused plugins; append `!` to auto-approve removal
"
" see :h vundle for more details or wiki for FAQ
" Put your non-Plugin stuff after this line
```
### Change Color scheme
- :colors [theme]

### Vim Airline plugin fonts fix
```
git clone https://github.com/powerline/fonts.git
```
```
cd fonts
```
```
./install.sh
```

### Fonts not rendering (update font--not effective with KDE Neon/Hack TTF)
```
mkdir ~/.local/share/fonts && cd ~/.local/share/fonts
```
```
wget https://github.com/source-foundry/Hack/releases/download/v3.003/Hack-v3.003-ttf.zip
```
```
p7zip hack*
```
```
fc-cache -f -v
```
