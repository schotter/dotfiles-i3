# .files

I'm using [ubuntu-mate](https://ubuntu-mate.org/download/) as a lightweight base.

## preparations

### gui

Install an icon set [arc-icon-theme](https://github.com/horst3180/arc-icon-theme)
and a mate theme [arc-theme](https://github.com/horst3180/Arc-theme).

```Bash
sudo apt install moka-icon-theme arc-theme
```

### tools

```Bash
sudo apt install git zsh kicad vim chromium-browser conky
```

```Bash
git clone git://github.com/robbyrussell/oh-my-zsh.git ~/.oh-my-zsh
chsh -s /bin/zsh
```

## i3

Thanks to
[i3wm: Jump start (1/3)](https://www.youtube.com/watch?v=j1I63wGcvU4),
[i3wm: Configuration (2/3)](https://www.youtube.com/watch?v=8-S0cWnLBKg) and
[i3wm: Rice up (3/3)](https://www.youtube.com/watch?v=ARKIwOlazKI)
i3 became my favorite window manager.

```Bash
sudo apt install i3blocks i3lock i3status
```

### fonts

The font [Font Awesome](https://github.com/FortAwesome/Font-Awesome) is used to beautify the screen.
Its file was already added to this repository.

## Cloning/Copying

Beautify git and fill in the user data.

```Bash
git config --global --add alias.glog 'log --all --decorate --oneline --graph'
git config --global core.editor "vim"
```

Clone this repository.

```Bash
git clone git@github.com:schotter/dotfiles.git .
```

And change mate's settings through `dconf`.

```Bash
dconf write /org/mate/caja/preferences/click-policy "'single'"
dconf write /org/mate/caja/preferences/thumbnail-limit "uint64 5242880"
dconf write /org/mate/caja/extensions/disabled-extensions "['folder-color', 'libcaja-wallpaper', 'libcaja-sendto']"
dconf write /org/mate/marco/general/theme "'Arc-Dark'"
dconf write /org/mate/desktop/interface/icon-theme "'Moka'"
dconf write /org/mate/desktop/interface/gtk-theme "'Arc-Dark'"
```

Well, including a simple configuration file instead of a list of instructions would be much nicer...

## Clean up

As long as there is a repository in the user's home folder every sub-folder is seen as  a part of that repository.
Therefore as a final step the git-folder must be removed.

```Bash
rm -rf ~/.git
rm ~/README.md
rm ~/.gitignore
```
