---
layout: post
title: My Development Environment
---
This is less a blog post and more a readme for a future version of myself to set up my development environment on a new machine. Eventually my goal is to create a [chef cookbook][chef], similar to [37signals cookbooks][37scookbooks], that would automate some of this. For now, a readme will have to suffice.

This guide is intended for the setup of an OSX machine. Parts should still be relevant for linux/unix users. As for Windows…why would you do that to yourself? 

*All* of the software listed in this guide is *free*.

## Xcode

The first thing you are going to do is install [Xcode][Xcode]. Pretty much everything you are going to try to install requires Xcode's compiler. Xcode usually takes about a billion years to download and install so go grab some food and let the waiting begin. 

Once the download is finished, start Xcode and open preferences (_cmd + ,_). Navigate to the downloads tab and install command line tools.

If you are a vim user, check out [Xvim][xvim]. It's a good way to get some core vim functionality in Xcode.

#### Alternatives

If you want to stay away from installing Xcode, there are a few alternatives.

##### Command Line Tools Only
For Lion and Mountian Lion users, apple now offers just the command line tools package without Xcode. You can download it from the [Apple Developer Site][command-line-tools]. 

##### OSX GCC Installer
This is a project maintained by [Kenneth Reitz][reitz] of [Heroku][heroku]. It gives you everything you need without Xcode. Check it out on [github][osx-gcc-installer].

## Homebrew

It's the OSX package manager. Check out the [homebrew][homebrew] on github for in more information. 

We are going to install:

* [git][git]
* [hub][hub] (note: git + hub = github)
* MacVim
* wget
* Zsh
* rbenv
* ruby-build

Install homebrew via the [documentation][homebrew-install] then brew install what you need:

	$ brew install git hub macvim wget zsh rbenv ruby-build

## rbenv

rbenv manages your Ruby versions. `ruby-build` is a plugin for `rbenv` that allows your to run `rbenv install` and build ruby with `rbenv`. Check out the [documentation][rbenv-docs] for more details.

	$ echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.zshrc
	$ echo 'eval "$(rbenv init -)"' >> ~/.zshrc
	$ rbenv install 1.9.3-p327
	$ rbenv global 1.9.3-p327

## Homesick

[Homesick][homesick] is a nifty little gem for managing your dotfiles. My dotfiles are at [cknadler/dotfiles][dotfiles] on github.

	$ gem install homesick
	$ homesick clone cknadler/dotfiles
	
## oh-my-zsh

[Oh-my-zsh][oh-my-zsh] is like a wardrobe and a toolbox for your terminal. Follow the [installation documentaiton][oh-my-zsh-install] and once you have it installed, run homesick symlink.

	$ homesick symlink cknadler/dotfiles
	
When asked if you want to overwrite, say yes to everything. 

## iTerm2 & Solarized

[iTerm2][iterm2] is awesome, but dont take my word for it. Here are [17 reasons] [iterm2-features] you should switch from *terminal.app*. 

So you have iTerm2 and it's great. There are all these new features and it's so much better than your old terminal. After a while though…it starts to get old… You slowly realize the honeymoon is over and you are trapped with with that awful default colorscheme. Enter [Solarized][solarized]. I pretty much use Solarized everywhere and with good reason. Solarized and iTerm2 go together like tech startups and beer.

Download or git clone [Solarized on github][solarized-github] and find the iTerm2 folder. There is [installation documentation][solarized-iterm2] on github (and in the folder). Once you finish installing it, restart your terminal and BAM, all is right with the world. 

So, I know exactly what you're thinking. Solarized is the best colorscheme my eyeballs have ever had the pleasure of viewing, I just wish I could get all of that beauty in Xcode. Sadly, Xcode support hasn't quite hit the main solarized repo at the time of writing, although chances are [it will soon][solarized-pull]. There is a fork, [brianmichel/solarized][solarized-brianmichel], with Xcode support and it works like a charm. Follow the  [installation-documentation][solarized-xcode-install] and you should be good to go. 

## Pow

[Pow][pow] is a no-brainer. If you've made it this far, you're a superhero in my book, so why not run your rails apps like one? Pow is a no-config devleopment server solution that allows you to spend more time being a superhero and less time screwing with `/etc/hosts`.

Thats it, my whole environment. If I something doesn't make sense or you have any questions ping me on twitter or send me an email. 

[chef]: http://wiki.opscode.com/display/chef/Home
[37scookbooks]: https://github.com/37signals/37s_cookbooks
[vagrant]: http://vagrantup.com/
[Xcode]: http://itunes.apple.com/us/app/xcode/id497799835?mt=12
[xvim]: https://github.com/JugglerShu/XVim
[osx-gcc-installer]: https://github.com/kennethreitz/osx-gcc-installer
[reitz]: http://www.kennethreitz.com/
[heroku]: http://www.heroku.com
[command-line-tools]: http://connect.apple.com
[homebrew]: https://github.com/mxcl/homebrew
[git]: http://git-scm.com
[hub]: https://github.com/defunkt/hub
[homebrew-install]: https://github.com/mxcl/homebrew/wiki/installation
[homesick]: https://github.com/technicalpickles/homesick
[dotfiles]: https://github.com/cknadler/dotfiles
[oh-my-zsh]: https://github.com/robbyrussell/oh-my-zsh
[oh-my-zsh-install]: https://github.com/robbyrussell/oh-my-zsh#the-automatic-installer%E2%80%A6-do-you-trust-me
[iterm2]: http://www.iterm2.com/
[iterm2-features]: http://www.iterm2.com/#/section/features
[solarized]: http://ethanschoonover.com/solarized
[solarized-github]: https://github.com/altercation/solarized
[solarized-iterm2]: https://github.com/altercation/solarized/tree/master/iterm2-colors-solarized#installation
[solarized-pull]: https://github.com/altercation/solarized/pull/30
[solarized-brianmichel]: https://github.com/brianmichel/solarized
[solarized-xcode-install]: https://github.com/brianmichel/solarized/tree/master/apple-xcode4-solarized#solarized---xcode-4-color-presets
[mou]: http://mouapp.com/
[quicksilver]: https://github.com/quicksilver/Quicksilver/
[droplr]: https://droplr.com/hello
[pow]: https://github.com/37signals/pow
[rbenv-docs]: https://github.com/sstephenson/rbenv#simple-ruby-version-management-rbenv

