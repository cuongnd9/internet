# internet

> Connect to the world | Setup VPN for Linux.

I am really happy to share the mini project that I made within 5 minutes. My company network has blocked almost all internet services so I feel too hard to work with 100%. GitHub is not, Google services are the same and that is the reason I create this project.

## Installation first

### 1. Setup WARP Client

```sh
sudo apt install cloudflare-warp
warp-cli register
warp-cli connect
curl https://www.cloudflare.com/cdn-cgi/trace/
```

### 2. Setup alias to turn on/off VPN

```sh
code ~/.zshrc
```

Add some "magic code" to .zshrc file.

```sh
alias warp='warp-cli connect'
alias warp-on='warp-cli connect'
alias warp-off='warp-cli disconnect'
alias warp-fix='sudo nano /etc/resolv.conf'
```

```sh
source ~/.zshrc
```

## And cheers

### Turn on VPN

```sh
warp
# or
warp-on
```

### Turn off VPN

```sh
warp-off
```

## Cloudflare warp no internet connection after off warp

<!-- 
```
sudo rm /etc/resolv.conf # Removes the config file, After this please open a diffren't console window!
``` -->

### Copy the DNS that starts with 192.x.x.x

> ifconfig

### Fix config Issue

> sudo nano /etc/resolv.conf

```yml
nameserver 8.8.8.8
nameserver 192.x.x.x # The DNS you copyied goes here
```
