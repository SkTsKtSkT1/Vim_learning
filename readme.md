# Install dein.vim &dein-ui.vim in windows



Dein.vim is a dark powered Vim/Neovim plugin manager

- [Requirements](#Requirement)
- [Quick start](#quick-start)
  - [Windows][#Windows]

## Requirements

- Vim 8.0 or above or NeoVim.

- "xcopy" command in $PATH (Windows)
  - You can find it at C:\Windows\System32,use powershell to verify it.
- "git" command in $PATH (if you want to install github or vim.org plugins)
- dein-ui.vim. https://github.com/wsdjeg/dein-ui.vim

##Quick-start

1. In powershell:

```powershell
Invoke-WebRequest https://raw.githubusercontent.com/Shougo/dein.vim/master/bin/installer.ps1 -OutFile installer.ps1
# Allow to run third-party script
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
# For example, we just use `~/.cache/dein` as installation directory
./installer.ps1 ~/.cache/dein
```

2. Edit _vimrc like this.

   ```vim
   if &compatible
     set nocompatible
   endif
   " Add the dein installation directory into runtimepath
   set runtimepath+=~/.cache/dein/repos/github.com/Shougo/dein.vim
   
   if dein#load_state('~/.cache/dein')
     call dein#begin('~/.cache/dein')
   
     call dein#add('~/.cache/dein/repos/github.com/Shougo/dein.vim')
     call dein#add('Shougo/deoplete.nvim')
     call dein#add('wsdjeg/dein-ui.vim') 
     if !has('nvim')
       call dein#add('roxma/nvim-yarp')
       call dein#add('roxma/vim-hug-neovim-rpc')
     endif
   
     call dein#end()
     call dein#save_state()
   endif
   
   filetype plugin indent on
   syntax enable
   ```

3. Open gvim and install dein

   ```vim
   :call dein#install()
   
   :call dein#recache_runtimepath()
   ```

4. Update the plugins.

   ```Vim
   :DeinUpdate
   ```

## Todo

1.Add some useful and helpful plugins to use vim much convenient.

2.Due to I am new to vim,I'll share some my ways to learn vim.

## Reference

1.https://github.com/Shougo/dein.vim

2.https://github.com/wsdjeg/dein-ui.vim

## Thanks

1. [Freed-Wu](https://github.com/Freed-Wu) help me to solve some problems and encourage me to use vim as a texteditor tool.

