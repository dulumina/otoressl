# Automatic Renew Certificate | otoressl

This tools for create cronjob for automaic renew certificate

## Dependencies
certbot
<br>
cronie

## Installing
- Download or clone this repo
- Give execute permition to script

```
git clone https://github.com/deadlyug/otoressl.git
cd otoressl
chmod +x otoressl config
```

## Configuring
Insert your Telegram bot token and chat id to config file
```
TOKEN_BOT_TELEGRAM="<your-random-bot-token-here>" # BOT TOKEN
ID_BOT_TELEGRAM="<your-chat-id-or-group-id-here" # Chat ID
```
### For UNTAD Admin 
You can download this for sending notify by telegram bot [otoressl](https://nextcloud.cloud.untad.ac.id/s/fjkwPifkxSFmT3L). 
- Download send-notify
> if you using CentOS7 download send-notify-centos7 and rename it to send-notify `mv send-notify-centos7 send-notify`
- Place the same directory with otoressl script

> dont forget to make the script executable by running `chmod +x send-notify`

## Using
> Make sure you have configured and installed ssl certificate on target host using certbot

run the script

```
./otoressl
```

or

```
source otoressl
```

or

```
bash otoressl
```

if you want to temporary disable firewall during the renewing, you can pass option like this 

```
./otoressl --disable-firewall <firewall service>
```

example

- using iptables
```
./otoressl --disable-firewall iptables
```
- using firewalld 
```
./otoressl --disable-firewall firewalld
```

## Tested
- [x] CentOS 7
- [ ] CentOS 8
- [ ] Ubuntu
- [ ] Arch

## Copyright
Copyright belongs to Allah
