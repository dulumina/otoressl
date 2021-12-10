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

### Via Webmin Console

```
certbot certificates
```

- Make sure you already configured and installed ssl certificate on target host using certbot
- Check expire time for each host if have multiple virtual host at the same server
- if each of virtual host have same expire time. it's okay to continue, if not. make sure the difference between expire time at least less than 10 days.

after you have checked the certificates, now you can run the script

if server using nginx

```
otoressl nginx -y
```

if server using apache

```
otoressl apache -y
```

> for other usecase you can follow method via **ssh** or **putty**, the difference only when you use **Webmin Console** you have to spesify option **-y**

:warning: **Webmin**: have to always use option -y, if you forget to spesify -y you have to cancel using <kbd>ctrl + c</kbd> if not the script cannot end, and it will be looping forever. maybe can make your server error. so please when use **Webmin Console** you have to spesify option **-y**

### Via ssh or putty 

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
otoressl apache
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
otoressl apache --disable-firewall firewalld
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
