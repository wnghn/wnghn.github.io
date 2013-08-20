---
layout: post
title: "Rake Aborted Error When Running Rake Generate after Ubuntu Reboot"
date: 2013-08-19 20:52
comments: true
categories: 脑热 
---
The Octopress blog environment was setup yesterday in my laptop and it ran quite well. But when I ran 
> rake generate

this morning after booting my Ubuntu, the following error message appeared:
>rake aborted!
cannot load such file -- bundler/setup

I googled and thought it was due to incorrect version settings of ruby or kramdown.  But the command to reset global ruby verison
> rbenv global 1.9.3-p0

gave me the following message:
> The program 'rbenv' is currently not installed.  You can install it by typing:
sudo apt-get install rbenv

This time I found the correct solution suggested in https://github.com/sstephenson/rbenv/issues/424,
which is 
> source ~/.bash_profile

in my case, since the path variable for rbenv was set there.