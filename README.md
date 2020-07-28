nerdtree-git-plugin
===================

A plugin of [NERDTree](https://github.com/preservim/nerdtree) showing git status flags.

The original project [git-nerdtree](https://github.com/Xuyuanp/git-nerdtree) will not be maintained any longer.

![Imgur](http://i.imgur.com/jSCwGjU.gif?1)

## Installation

Use your favorite package manager. Here is the example of using [vim-plug](https://github.com/junegunn/vim-plug)

```vim script
Plug 'preservim/nerdtree' |
            \ Plug 'Xuyuanp/nerdtree-git-plugin'
```

## FAQ

> Got error message like `Error detected while processing function
177[2]..178[22]..181[7]..144[9]..142[36]..238[4]..NERDTreeGitStatusRefreshListener[2]..NERDTreeGitStatusRefresh:
line 6:
E484: Can't open file /tmp/vZEZ6gM/1` while nerdtree opening in fish, how to resolve this problem?

This was because that vim couldn't execute `system` function in `fish`. Add `set shell=sh` in your vimrc.

This issue has been fixed.

> How to config custom symbols?

Use this variable to change symbols.

```vim
let g:NERDTreeGitStatusIndicatorMapCustom = {
    \ "Modified"  : "✹",
    \ "Staged"    : "✚",
    \ "Untracked" : "✭",
    \ "Renamed"   : "➜",
    \ "Unmerged"  : "═",
    \ "Dirty"     : "✗",
    \ "Ignored"   : "☒",
    \ }
```

There is a predefined map used *nerdfonts*, to enable it

```vim
let g:NERDTreeGitStatusUseNerdFonts = 1 " you should install nerdfonts by yourself. default: 0
```

> How to show `ignored` status?

```vim
let g:NERDTreeGitStatusShowIgnored = 1 " a heavy feature may cost much more time. default: 0
```

> How to cooperate with [vim-devicons](https://github.com/ryanoasis/vim-devicons)

```vim
Plug 'preservim/nerdtree' |
            \ Plug 'Xuyuanp/nerdtree-git-plugin' |
            \ Plug 'ryanoasis/vim-devicons'
```

Make sure they are in the right order.

> How to indicate every single `untracked` file under an `untracked` dir?

```vim
let g:NERDTreeGitStatusUntrackedFilesMode = 'all' " a heave feature too. default: normal
```

> How to set `git` executable file path?

```vim
let g:NERDTreeGitStatusGitBinPath = '/your/file/path' " defualt: git (auto find in path)
```

## Credits

*  [scrooloose](https://github.com/scrooloose): Open API for me.
*  [git\_nerd](https://github.com/swerner/git_nerd): Where my idea comes from.
*  [PickRelated](https://github.com/PickRelated): Add custom indicators & Review code.
