# vagrant-htb

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
cd vagrant-htb
vagrant up
```

## Socks Proxy set-up

```
ssh vagrant@10.13.37.10 -D 1234
```

On native OS, set Socks Proxy on Burp Suite
```
10.13.37.10
1234
```

Happy hacking
