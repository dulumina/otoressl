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
#### For UNTAD Admin 
You dont need to configure config file, just download this file with wget command
```
wget https://nextcloud.cloud.untad.ac.id/s/34Hc6MsrwpC6CjF/download/send-notify --no-check-certificate
```
dont forget to make the script executable by running `chmod +x send-notify`
> make sure place send-notify script in same forder with otoressl script

## Using
- Make sure you already configured and installed ssl certificate on target host using certbot
- Check expire time for each host if have multiple virtual host at the same server
```
certbot certificates
```
> if each of virtual host have same expire time. it's okay to continue, if not. make sure the difference between expire time at least less than 10 days.

- run the script

```
./otoressl <web-server-service>
```

or

```
source otoressl
```

or

```
bash otoressl
```

example

```
./otoressl nginx
```

or

```
./otoressl httpd
```

- if you want to temporary disable firewall during the renewing, you can pass option like this 

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
