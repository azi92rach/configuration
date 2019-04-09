# configuration

## Clone the configuration
```
git clone https://github.com/azi92rach/configuration.git
```

## TMUX

For Mac:
```
brew install libevent
brew install tmux
ln -s ~/configuration/.tmux.conf ~/.tmux.conf
git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
tmux
tmux source ~/.tmux.conf
```

For Linux: 

```
sudo apt-get install -y automake build-essential pkg-config libevent-dev libncurses5-dev
wget https://github.com/tmux/tmux/releases/download/2.8/tmux-2.8.tar.gz
tar -zxvf tmux-2.8.tar.gz
cd tmux-2.8
./configure && make
sudo make install
ln -s ~/configuration/.tmux.conf ~/.tmux.conf
git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
tmux
tmux source ~/.tmux.conf
```

## SPACEEMACS

NOTE: You need a version of emacs 24.4 of higher.

For EC2:
```
sudo yum install gtk2-devel
wget https://ftp.gnu.org/gnu/emacs/emacs-26.1.tar.gz
tar -zxvf emacs-26.1.tar.gz
cd emacs-26.1
./configure --with-gnutls=no --with-mailutils
make
sudo make install
cd ..
rm -rf emacs-*
git clone https://github.com/syl20bnr/spacemacs ~/.emacs.d
ln -s ~/configuration/.spacemacs ~/.spacemacs
```

For Linux
```
sudo apt-get install -y xsel build-essential gcc g++ texinfo libx11-dev libxpm-dev libjpeg-dev libpng-dev libgif-dev libtiff-dev libgtk2.0-dev libncurses-dev gnutls-bin libcanberra-gtk-module libcanberra-gtk3-module
wget http://mirrors.kernel.org/gnu/emacs/emacs-26.1.tar.gz
tar -zxvf emacs-26.1.tar.gz
cd emacs-26.1
./configure --with-gnutls=no --with-mailutils
make
sudo make install
cd ..
rm -rf emacs-*
git clone https://github.com/syl20bnr/spacemacs ~/.emacs.d
ln -s ~/configuration/.spacemacs ~/.spacemacs
```

## DOCKER 

```
sudo apt-get install -y apt-transport-https ca-certificates curl software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo apt-key fingerprint 0EBFCD88
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
sudo apt-get update
sudo apt-get install -y docker-ce
sudo usermod -aG docker $USER
grep 'docker' /etc/group

sudo curl -L https://github.com/docker/compose/releases/download/1.23.1/docker-compose-$(uname -s)-$(uname -m) -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
sudo reboot
```
