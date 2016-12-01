# utilitarios-vps-ssh
Repositório indicado apenas configurações (SSH and Proxy) e utilitários.

# Utilitários

> Importante: Antes de adicionar os scripts abaixo, digite o seguinte comando:
```
awk -F : '$3 >= 500 { print $1 " 1" }' /etc/passwd | grep -v '^nobody' > /root/usuarios.db
```

**Adicionar host**
```
http://pastebin.com/raw/zAtfDqie
```

**Alterar senha de um Usuario**
```
http://pastebin.com/raw/zAtfDqie
```

**Criar Usuario SSH**
```
http://pastebin.com/raw/zAtfDqie
```

**Deletar Host**
```
http://pastebin.com/raw/zAtfDqie
```

**Limpar Expirados**
```
http://pastebin.com/raw/zAtfDqie
```

**Mudar Data de Expiração de um Usuario**
```
http://pastebin.com/raw/zAtfDqie
```


# Proxy ( Squid Completo )
```
nano /etc/squid3/squid.conf
```
```
acl url1 dstdomain -i 127.0.0.1
acl url2 dstdomain -i localhost
acl url3 dstdomain -i DIGITE AQUI O IP DA SUA VPS

acl payload dstdomain -i "/etc/squid3/payload.txt"
acl bloq url_regex -i "/etc/squid3/bloq"
acl telegram src telegram.me
acl netflix dstdomain .netflix.
acl torrent url_regex ?i \.torrent$

http_access allow url1
http_access allow url2
http_access allow url3
http_access allow netflix
http_access allow payload

http_access deny all
http_access deny bloq
http_access deny torrent

http_port 80
http_port 3128
http_port 8080
http_port 8799

visible_hostname vpsmanager

forwarded_for off
via off
```
