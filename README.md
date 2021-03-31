# Конфиги для всякоразного:  
  
## Openbox-Kiosk  
[autostart](openbox/autostart)  
- Автостарт chromium для openbox в kiosk-e  
-- path для Debian  
```/etc/xdg/openbox/autostart```  
  
## Openvpn  
  
### Openvpn-client  
[client.conf](openvpn/client.conf)  
Шаблон для клиентского конфига openvpn  
-- path для Debian  
--- [client-name] не обязательно совпадает с именами из сертификатов  
или именем хоста, но удобно когда это так  
```/etc/openvpn/client/[client-name].conf```  
```systemctl start openvpn-client@[client-name]```  
  
### Openvpn-server  
[server.conf](openvpn/server.conf)  
Шаблон для конфига openvpn-server  
-- все paths для CentOS7  
```/etc/openvpn/server.conf```  
#### easy-rsa  
># TODO migrate to easy-rsa 3.0  
[easy-rsa/](openvpn/easy-rsa/)  
Генерация сертификатов для сервера и клиентов  
##### openssl.cnf  
Конфигурация easy-rsa для генерации rsa  
[openssl.cnf](openvpn/easy-rsa/openssl.cnf)  
```/etc/openvpn/easy-rsa/openssl.cnf```  
##### vars  
Конфиг самовыписываемых сертификатов для  
[vars](openvpn/easy-rsa/vars)  
```/etc/openvpn/easy-rsa/vars```  
##### keys  
Папка куда генерируются ключи по умолчанию  
[keys/](openvpn/easy-rsa/keys/)  
```/etc/openvpn/easy-rsa/keys/```  
##### index.txt  
База easy-rsa для последовательных сертификатов,  
служебный файл easy-rsa, но можно использовать  
[index.txt](openvpn/easy-rsa/keys/index.txt)  
```/etc/openvpn/easy-rsa/keys/index.txt```  
##### serial  
Следующий индекс для генерации сертификата,  
служебный файл easy-rsa, но можно использовать  
[serial](openvpn/easy-rsa/keys/serial)  
```/etc/openvpn/easy-rsa/keys/serial```  
#### Статические IP для клиентов  
##### ipp.txt  
Файл со списком статических IP клиентов,  
Список имя клиента(KEY_CN) ip адрес:  
```KEY_CN, ip```   
[ipp.txt](openvpn/ipp.txt/)  
```/etc/openvpn/ipp.txt```  
##### ccd  
Файлы со статискими IP клиентов,  
Имя файла = KEY_CN  
Содержание = ```ifconfig-push [ip] [mask]```  
Соотвественно по файлу на каждый клиент  
[ccd](openvpn/ccd/client)  
```/etc/openvpn/ccd/client```  
  
## System mail clients  
  
### CentOS7 (mailx)  
[mail.rc](system_mail_clients/mail.rc)  
```/etc/mail.rc```  
  
### Debain (exim4)  
```/etc/exim4/update-exim4.conf.conf```  
```/etc/exim4/exim4.conf.localmacros```  
```/etc/exim4/exim4.conf.template```  
```/etc/exim4/passwd.client```  
```/etc/email-addresses```  
  
## Nginx  
[nginx/](nginx/)  
Шаблоны конфигов для нжинкса  
  
## Debian-preseed  