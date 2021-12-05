# Linux Config Cheatsheet
To start from zero for Debian||Ubuntu

Setup minimal packages
```
apt-get update && apt-get install -y git-core sudo curl fail2ban zsh vim htop dnsutils
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
#...
export LC_ALL="en_US.UTF-8"
export LANGUAGE="en_US.UTF-8"
#...
alias wanip="dig +short myip.opendns.com @resolver1.opendns.com"
alias weather="curl wttr.in/krasnoyarsk"
```
```
source ~/.zshrc
```
If troubles with Agnoster theme - use this fonts ((anon):12: character not in range).
Don't forget restart session
```
cd ~/.oh-my-zsh && git clone https://github.com/powerline/fonts.git --depth=1 && cd fonts && ./install.sh && cd .. && rm -rf fonts
```
ensure you have locales
```
apt-get install -y locales locales-all
```
Syntax highlighting
```
cd ~/.oh-my-zsh
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git
echo "source ${(q-)PWD}/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh" >> ${ZDOTDIR:-$HOME}/.zshrc
source ~/.zshrc
```
Swap file
```
sudo fallocate -l 4G /swapfile &&
sudo chmod 600 /swapfile &&
sudo mkswap /swapfile &&
sudo swapon /swapfile &&
free -m
```
Install Nginx
```
apt-get update && apt-get install -y nginx
```
Create DB user, database and grant  privileges
```
CREATE DATABASE dbName;
GRANT ALL PRIVILEGES ON dbName.* To 'user'@'localhost' IDENTIFIED BY 'password';
```
