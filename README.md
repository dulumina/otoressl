# Automatic Renew Certificate | otoressl

This tools for create cronjob for automaic renew certificate

## Dependencies
certbot
<br>
cronie

## Installing
```
curl -s https://raw.githubusercontent.com/deadlyug/otoressl/v1.0.1/install | bash
```

#### FOR UNTAD Admin
```
curl -s https://raw.githubusercontent.com/deadlyug/otoressl/v1.0.1/install-untad-admin | bash
```

## Configuring
Insert your Telegram bot token and chat id to config file
```
TOKEN_BOT_TELEGRAM="<your-random-bot-token-here>" # BOT TOKEN
ID_BOT_TELEGRAM="<your-chat-id-or-group-id-here" # Chat ID
```
#### For UNTAD Admin 
You dont need to configure config file. 

## Using
run the script

```
otoressl <web-server-service>
```

example

```
otoressl nginx
```

or

```
otoressl httpd
```

if you want to temporary disable firewall during the renewing, you can pass option like this 

```
otoressl <web-server-service> --disable-firewall <firewall-service>
```

example

- using iptables
```
otoressl nginx --disable-firewall iptables
```
- using firewalld 
```
otoressl httpd --disable-firewall firewalld
```

if you want to restart webmin after renew certificate


```
otoressl <web-server-service> --restart-webmin
```

or with disable firewall

```
otoressl <web-server-service> --disable-firewall <firewall-service> --restart-webmin
```

## Tested
- [x] CentOS 7
- [ ] CentOS 8
- [x] Ubuntu 20.04
- [ ] Arch

## Copyright
Copyright belongs to Allah
