---
title: Vim
author: csmertx
date: February 4, 2023
weight: -20
---

## Cut/Copy Paste Registers not working

- ```vim ~/.vimrc```

    ```
    -- set clipboard+=unnamed
    ++ set clipboard=unnamed
    ```

## Spellcheck

- vim ~/.vimrc

    ```
    ++ set spell spelllang=en_us
    ```

- Movement

    - ```]``` + ```s``` = Next misspelled word

    - ```[``` + ```s``` = Prev misspelled word

- Suggestions

    - ```z``` + ```=```

- Add to dictionary

    - ```z``` + ```g```

- Mark for later

    - ```z``` + ```w```

- turn off with ```:set nospell```

    > Or edit ```~/.vimrc``` and add ```:map <F7> :setlocal spell! spelllang=en_us<CR>``` to toggle with ```F7```

## Vundle Installation

- ```git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim```

- If ```cp ~/.vim``` then load vim and run: ```:PluginUpdate```

    > If you copied ~/.vim from another system just run the above command to update plugins

- ```vim ~/.vimrc```

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
    > See [below](#resources-vim-plugins--colorschemes) for plugin links

## View or edit encrypted documents with Vim

- Vundle: https://github.com/jamessan/vim-gnupg

- Example: ```vim example.txt.gpg```

    - enter ```password``` to save and exit

- ```vim ~/.{bas,zs,fis}hrc```
    
    ```
    ++ GPG_TTY=$(tty)
    ++ export GPG_TTY
    ```

## Turn off auto backup

- ```vim ~/.vimrc```
    
    ```
    ++ set nobackup
    ++ set nowritebackup
    ```

## Change Color scheme

- ```vim ~/.vimrc```

    ```
    ++ colorscheme challenger_deep
    ```

    > See [below](#resources-vim-plugins--colorschemes) for themes

## Vim Airline plugin fonts fix

- ```git clone https://github.com/powerline/fonts.git```

- ```cd fonts```

- ```./install.sh```

## Fonts not rendering

> Update font cache--not effective with KDE Neon/Hack TTF?

- ```mkdir ~/.local/share/fonts && cd ~/.local/share/fonts```

- ```wget https://github.com/source-foundry/Hack/releases/download/v3.003/Hack-v3.003-ttf.zip```

- ```p7zip hack*```

- ```fc-cache -f -v```

## Resources

- [Vim Homepage](https://www.vim.org/)

- [GitHub - vim/vim: The official Vim repository](https://github.com/vim/vim)

- [GitHub - philc/vimium: The hacker&#39;s browser](https://github.com/philc/vimium)

- [GitHub - VundleVim/Vundle.vim: Vundle, the plug-in manager for Vim](https://github.com/VundleVim/Vundle.vim)

- [GitHub - csmertx/dotfiles: configs, scripts, etc.](https://github.com/csmertx/dotfiles)

### Resources (Vim Plugins / Colorschemes)

- [GitHub - VundleVim/Vundle.vim: Vundle, the plug-in manager for Vim](https://github.com/VundleVim/Vundle.vim)

- [GitHub - vim-airline/vim-airline: lean &amp; mean status/tabline for vim that&#39;s light as air](https://github.com/vim-airline/vim-airline)

- [GitHub - vim-airline/vim-airline-themes: A collection of themes for vim-airline](https://github.com/vim-airline/vim-airline-themes)

- [GitHub - ctrlpvim/ctrlp.vim: Active fork of kien/ctrlp.vim—Fuzzy file, buffer, mru, tag, etc finder](https://github.com/ctrlpvim/ctrlp.vim)

- [GitHub - preservim/nerdtree: A tree explorer plugin for vim.](https://github.com/preservim/nerdtree)

- [GitHub - henrik/vim-indexed-search: Show "Match 123 of 456  /search term/" in Vim searches](https://github.com/henrik/vim-indexed-search)

- [GitHub - godlygeek/tabular: Vim script for text filtering and alignment](https://github.com/godlygeek/tabular)

- [GitHub - Yggdroot/indentLine: A vim plugin to display the indention levels with thin vertical lines
](https://github.com/Yggdroot/indentLine)

- [GitHub - vim-syntastic/syntastic: Syntax checking hacks for vim](https://github.com/vim-syntastic/syntastic)

- [GitHub - lervag/vimtex: VimTeX: A modern Vim and neovim filetype plugin for LaTeX files](https://github.com/lervag/vimtex)

- [GitHub - xuhdev/SingleCompile: A Vim plugin making it more convenient to compile or run a single source file](https://github.com/xuhdev/SingleCompile)

- [GitHub - dracula/vim: 🧛🏻‍♂️ Dark theme for Vim](https://github.com/dracula/vim)

- [GitHub - rafi/awesome-vim-colorschemes: Collection of awesome color schemes](https://github.com/rafi/awesome-vim-colorschemes)