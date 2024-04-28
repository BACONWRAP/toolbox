
# DOTFILES


[shamelessly stolen](https://www.atlassian.com/git/tutorials/dotfiles)


## Things to install:

- zsh - from apt
- [oh-my-zsh](https://ohmyz.sh/) - from link
- [powerlevel10k](https://github.com/romkatv/powerlevel10k) - from link
- gh(cli) - from apt

### to install:
```
alias config='/usr/bin/git --git-dir=$HOME/.mycfg/ --work-tree=$HOME'
```

```
echo ".mycfg" >> .gitignore
```

```
git clone --bare git@github.com:BACONWRAP/dotfiles.git $HOME/.mycfg
```

```
config checkout
```

if files conflict, run:
```
mkdir -p .config-backup && \
config checkout 2>&1 | egrep "\s+\." | awk {'print $1'} | \
xargs -I{} mv {} .config-backup/{}
```

don't track your whole home folder dummy:
```
config config --local status.showUntrackedFiles no
```
