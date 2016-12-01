# utilitarios-vps-ssh
Repositório indicado apenas configurações (SSH and Proxy) e utilitários.

# Scripts Úteis

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

**Remover Usuario**
```
http://pastebin.com/raw/zAtfDqie
```

**Limitar Conexão Simultanea**
```
http://pastebin.com/raw/zAtfDqie
```

**Alterar Limite Conexões simultanea Usuario Especifico**
```
http://pastebin.com/raw/zAtfDqie
```

**SSH Monitor**
```
http://pastebin.com/raw/zAtfDqie
```
**EXEMPLO DE INSTALAÇÃO**

```
wget http://pastebin.com/raw/zAtfDqie -O /bin/addhost
```

```
chmod +x /bin/addhost
```

**Logo em seguida para executar o script, digite o nome do mesmo, ex:**

```
addhost
```

>Troque o link do pastebin acima, para o do script que você deseja.

# Proxy ( Squid Completo )

```
nano /etc/squid3/squid.conf
```

```
#IMPEDIR USAR SEU PROXY EM OUTRAS SSH
acl url1 dstdomain -i 127.0.0.1
acl url2 dstdomain -i localhost
acl url3 dstdomain -i DIGITE AQUI O IP DA SUA VPS

acl payload dstdomain -i "/etc/squid3/payload.txt"
acl bloq url_regex -i "/etc/squid3/bloq"
acl telegram src telegram.me
acl netflix dstdomain .netflix.
acl torrent url_regex ?i \.torrent$

#PERMISSÃO DE ACESSO LIBERADOS

http_access allow url1
http_access allow url2
http_access allow url3
http_access allow netflix
http_access allow payload

#PERMISSÃO DE ACESSO BLOQUEADOS
http_access deny all
http_access deny bloq
http_access deny torrent

#PORTAS DE ACESSO NO SQUID
http_port 80
http_port 3128
http_port 8080
http_port 8799

visible_hostname vpsmanager

forwarded_for off
via off
```
