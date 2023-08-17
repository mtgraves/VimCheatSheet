# VimCheatSheet
personal vim cheat sheet

#### Add to end of every line containing certain characters

to find every line that has `stuff` in it and add `things` to the end of that line:

```vim
:%s/stuff.*/\0things
```

from visual mode with highlighted blocks, issue `:` which will give you something like

```vim
:'<,'>s/stuff.*/\0things
```
