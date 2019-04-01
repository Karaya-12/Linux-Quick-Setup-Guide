# Linux Quick Setup Guide

Ubuntu LTS Version (Currently 18.04.02 Bionic Beaver) Quick Installation Guide

* Mainly for Self-use

## 1. Ubuntu Installation Guide

### 1.1 Mounting Partitions

1. /  -->  20 GB
2. /home -->  All Free Space
3. /boot  -->  Won't Be Needed
4. swap  -->  2000 MB

### 1.2 Terminal Customization

1. Background Color  -->  #2E2E2E
2. Text Color  -->  #3790FF
3. Custom Font  -->  Monospace Regular 12
4. Use Transparent Background  -->  Approximately 30%
5. Built-in Schemes  -->  XTerm
6. Cursor Shape  -->  I-Beam

### 1.3 Grub Default Boot Setting

```
$ sudo gedit /etc/default/grub
```
Set to:  `GRUB_DEFAULT=2`

```
$ sudo update-grub
```

### 1.4 Synchronize Time Zone

```
$ sudo apt-get install ntpdate
$ sudo ntpdate time.windows.com / sudo ntpdate -d 182.92.12.11
$ sudo hwclock --localtime --systohc
```

### 1.5 Update "apt" Source

Hit "Windows" Button --> Software & Updates

## 2 Basic Softwares & System Customization

### 2.1 System Customization

I've Chosen macOS As My Ubuntu Customization Style

https://blog.csdn.net/lishanleilixin/article/details/80453565  
https://blog.csdn.net/ice__snow/article/details/80152068

### 2.2 Install GNOME Tweaks

```
$ sudo apt install gnome-tweak-tool
$ sudo apt install gnome-shell-extensions
$ sudo apt install chrome-gnome-shell
$ sudo apt install gtk2-engines-pixbuf
$ sudo apt install libxml2-utils
```

### 2.3 Setting Fonts

Bitstream Charter Bold 14 
Bitstream Charter Regular 13

### 2.4 Setting Icon --> Ultra Flat

```
$ sudo add-apt-repository ppa:noobslab/icons
$ sudo apt update
$ sudo apt install ultra-flat-icons
```

### 2.5 * Sogou Input + fctix (May Cause Problems)

Download The Latest Pack from:

https://pinyin.sogou.com/linux/?r=pinyin

```
$ sudo apt-get install fcitx-bin
$ sudo apt-get update --fix-missing
$ sudo apt-get install fcitx-bin     # Reinstall After Fixing
$ sudo apt-get install fcitx-table
$ reboot
```

### 2.6 Install Firefox / Chrome

## 3 Install Coding Tools

### 3.1 VS Code

https://code.visualstudio.com/

### 3.2 Pycharm / Intellij IDEA / CLion / PhpStorm / DataGrip etc.

1. Check Out JetBrain's Official Site
2. Extract & Check Out `Install-Linux-tar.txt`
   - or
   ```
   cd ./bin
   ./xxx.sh
   ```
3. Tools --> Create Desktop Entry

### 3.3 Anaconda + Jupyter Notebook

Jupyter Notebook Will be Included In Anaconda

### 3.4 Install JDK

Latest Version For The Time Being - OpenJDK 12

1. Using apt Repository to Install OpenJDK 12

```
$ sudo add-apt-repository ppa:linuxuprising/java
$ sudo apt update
$ sudo apt install oracle-java12-installer
```

2. Making Oracle Java 12 Default

```
$ sudo apt install oracle-java12-set-default
```

### 3.5 Install MySQL 8

Check Out

https://dev.mysql.com/doc/mysql-apt-repo-quick-guide/en/  
https://blog.csdn.net/zyqblog/article/details/80159990

```
$ wget -c https://dev.mysql.com/get/mysql-apt-config_0.8.12-1_all.deb
$ sudo dpkg -i mysql-apt-config_0.8.12-1_all.deb
$ sudo apt update
$ sudo apt install mysql-server
```

### 3.6 Install Sublime Text 3

http://www.sublimetext.com/docs/3/linux_repositories.html

* Package Control Addon

## 4 Nvidia Driver

Check Out

https://blog.csdn.net/tjuyanming/article/details/80862290

```
$ sudo apt purge nvidia-*
$ sudo add-apt-repository ppa:graphics-drivers/ppa
$ sudo apt update
$ sudo apt install nvidia-xxx
```

## 5 MISC

### 5.1 Install Git

```
$ sudo apt install git
```

### 5.2 Install Vim

```
$ sudo apt install vim
```

### 5.3 Install Shutter

```
$ sudo apt install shutter
```

### 5.4 Install BleachBit Stacer

```
$ sudo apt-get install bleachbit & https://github.com/oguzhaninan/Stacer/releases
```

### 5.5 Typora

```
$ wget -qO - https://typora.io/linux/public-key.asc | sudo apt-key add -
$ sudo add-apt-repository 'deb https://typora.io/linux ./'
$ sudo apt-get update
$ sudo apt-get install typora
```

### 5.6 Install Clementine

```
$ sudo add-apt-repository ppa:me-davidsansome/clementine
$ sudo apt update
$ sudo apt install clementine
```

### 5.7 Install VLC Media Player

Check Out The New Ubuntu Software Shop

### 5.8 Electron SSR

Check Out

https://github.com/erguotou520/electron-ssr

### 5.9 Install Zenmap (Optional)

```
$ sudo apt install nmap / zenmap
```

## 6 System Crashing & Fixing

### 6.1 Ubuntu Safe Reboot

```
1. Hold "Clt + Alt + Prt Sc" for 3s
2. Release "Prt Sc"
3. Type "reisub" (busier) While Holding "Clt + Alt"
```

### 6.2 IME(Input Method Editor) Crashing (CHS IME)

Sogou IME's Supporting for Linux System is TERRIBLE.

Just Remove Sogou IME & fctix Completely

```
Clt + Alt + F2
$ sudo apt remove sogoupinyin
$ sudo apt remove fctix
$ sudo apt autoremove
```