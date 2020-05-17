# Vagrant-htb

## Kali vagrant setup (minimal)

__Tools installed__

  - vim
  - net-tools
  - python3
  - unzip
  - tmux
  - nmap
  - webshells
  - docker-ce

If you want to add more, just edit the provision/kali.yml file. 

__Fancy Git repo's added__

  - Impacket
  - Nishang

Againg, if you want to add more just append the git repo blocks within the provision/kali.yml

## Install VirtualBox

__MacOS/Windows/Unix__
```
https://www.virtualbox.org/wiki/Downloads
```

## Install Vagrant

__MacOS/Windows/Unix__
```
https://www.vagrantup.com/downloads.html
```

## Start Kali box

```
git clone git@github.com:moatn/vagrant-htb.git
cd vagrant-htb
vagrant up
```

## Socks Proxy set-up

The vagrant machine automatically sets up a Socks Proxy. This way, you can use your Burp Suite on your Native OS ;-) 

On native OS, set Socks Proxy wihtin Burp Suite
```
127.0.0.1
1080
```

## Enter vagrant machine

```
vagrant ssh kali01 
```

Happy hacking
