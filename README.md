# Linux Config Cheatsheet
To start from zero for Debian||Ubuntu

Setup minimal packages
```
apt-get update && apt-get install -y git-core sudo curl fail2ban zsh vim
```
Fix locale
```
apt install --reinstall locales
dpkg-reconfigure locales
sudo update-locale LC_ALL=en_US.UTF-8 LANG=en_US.UTF-8 LANGUAGE=en_US.UTF-8
source ~/.zshrc
```
Oh my Zsh (auto)
```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```
Oh my Zsh (manual, optional)
```
git clone https://github.com/robbyrussell/oh-my-zsh.git ~/.oh-my-zsh
chsh -s /bin/zsh
```
Custom config
```
vim ~/.zshrc
```
```
ZSH_THEME="agnoster" 
...
alias wanip="dig +short myip.opendns.com @resolver1.opendns.com"
alias weather="curl wttr.in/krasnoyarsk"
```
```
source ~/.zshrc
```
If troubles with Agnoster theme - use this fonts ((anon):12: character not in range)
```
cd ~/.oh-my-zsh

git clone https://github.com/powerline/fonts.git --depth=1

cd fonts && ./install.sh

cd .. && rm -rf fonts
```
Syntax highlighting
```
cd ~/.oh-my-zsh
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git
echo "source ${(q-)PWD}/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh" >> ${ZDOTDIR:-$HOME}/.zshrc
```
