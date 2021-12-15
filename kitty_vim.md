# How can I use Vim with Kitty without getting the 'E32: No file name' error?

You can just tell vim to write to `/dev/null`.
The following line is from my `kitty.conf` and does this:
```
map alt+v launch --type=overlay --stdin-source=@screen_scrollback  nvim -c 'set ft=man | :$ | :normal k' - +'w! /dev/null'
```
