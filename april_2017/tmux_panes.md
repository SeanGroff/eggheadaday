## [Organize your terminal using tmux panes](https://egghead.io/lessons/tools-organize-your-terminal-using-tmux-panes?course=wrangle-your-terminal-with-tmux)

### Example
On OS X tmux can be install using homebrew
```
> brew install tmux
```
You can change the default behavior of tmux with the Tmux config file
```
> vim ~/.tmux.conf
```
#### How to start a Tmux session from the terminal
```
> tmux
```
#### Default Prefix key
```
> Ctrl + b
```
#### Create a new pane vertically
```
> Ctrl + b %
```
#### Create a new pane horizontally
```
> Ctrl + b "
```
#### Switch between panes using the prefix key and the appropriate arrow key
```
> Ctrl + b Left Arrow
> Ctrl + b Right Arrow
> Ctrl + b Up Arrow
> Ctrl + b Down Arrow
```
#### You can change your prefix key from Ctrl + b to something else
```
> vim ~/.tmux.conf
> unbind-key C-b
> set -g prefix C-Space
```
This will set your prefix key to Ctrl + Space

### Tweet
<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Organize your terminal using tmux panes - otherjs Video Tutorial <a href="https://twitter.com/hashtag/free?src=hash">#free</a> <a href="https://twitter.com/eggheadio">@eggheadio</a>: <a href="https://t.co/7161VQpl08">https://t.co/7161VQpl08</a><br>By: <a href="https://twitter.com/brindelle">@brindelle</a> <a href="https://twitter.com/hashtag/eggheadADay?src=hash">#eggheadADay</a> <a href="https://twitter.com/hashtag/tmux?src=hash">#tmux</a></p>&mdash; Sean Groff (@_SeanGroff) <a href="https://twitter.com/_SeanGroff/status/852537341654818818">April 13, 2017</a></blockquote>

### Github Contributor
[@SeanGroff](https://github.com/SeanGroff) :koala:

##### Date - 04/13/2017
___
