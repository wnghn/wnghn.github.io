---
layout: post
title: "Rake Aborted Error When Running Rake Generate after Ubuntu Reboot"
date: 2013-08-20 13:32
comments: true
categories: Octopress
---
The Octopress blog environment was setup yesterday in my laptop and it ran quite well. But when I ran `rake generate` this morning after booting my Ubuntu, the following error message appeared:
>rake aborted!
cannot load such file -- bundler/setup

I googled and thought it was due to incorrect version settings of ruby or kramdown.  But the command to reset global ruby verison `rbenv global 1.9.3-p0`
gave me the following message:
> The program 'rbenv' is currently not installed.  You can install it by typing:
sudo apt-get install rbenv

This time I found the correct **SOLUTION** suggested in [Ubuntu - The program 'rbenv' is currently not installed. You can install it by typing: sudo apt-get install rbenv][1],
which is 
```
source ~/.bash_profile
```
in my case, since that's where the path to rbenv is included by environment variables during my installation of rbenv. To see why `~/.bash_profile` is not automatically sourced in Ubuntu, have a look at [Why ~/.bash_profile is not getting sourced when opening a terminal?][2].


  [1]: https://github.com/sstephenson/rbenv/issues/424
  [2]: http://askubuntu.com/questions/121073/why-bash-profile-is-not-getting-sourced-when-opening-a-terminal