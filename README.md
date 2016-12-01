# utilitarios-vps-ssh
Repositório indicado apenas configurações (SSH and Proxy) e utilitários.

# OS Distri Linux Recomendados para Uso de SSH and Proxy

| Debian | Ubuntu |
| :---         |          ---: |
| Debian 7 64bit   | Ubuntu Server 14.04 LTS 64bit    |
| Debian 8 64bit     | Ubuntu Server 16.04 LTS 64bit      |

# Scripts Úteis

> Importante: Antes de adicionar os scripts abaixo, digite o seguinte comando:
```
awk -F : '$3 >= 500 { print $1 " 1" }' /etc/passwd | grep -v '^nobody' > /root/usuarios.db
```

**Adicionar host**
```
wget http://pastebin.com/raw/zAtfDqie -O /bin/addhost

chmod +x /bin/addhost

```

**Alterar senha de um Usuario**
```
wget http://pastebin.com/raw/i8Fve3PT -O /bin/alterarsenha

chmod +x /bin/alterarsenha
```

**Criar Usuario SSH**
```
wget http://pastebin.com/raw/X1j2zRDW -O /bin/criarusuario

chmod +x /bin/criarusuario
```

**Deletar Host**
```
wget http://pastebin.com/raw/4kTeb5cE -O /bin/delhost

chmod +x /bin/delhost

Digite o comando: "delhost" sem as aspas
```

**Limpar Expirados**
```
wget http://pastebin.com/raw/Lrr11kiS -O /bin/expcleaner

chmod +x /bin/expcleaner
```

**Mudar Data de Expiração de um Usuario**
```
wget http://pastebin.com/raw/zAtfDqie -O /bin/mudardata

chmod +x /bin/mudardata
```

**Remover Usuario**
```
wget http://pastebin.com/raw/zAtfDqie -O /bin/remover

chmod +x /bin/remover
```

**Limitar Conexão Simultanea**
```
wget http://pastebin.com/raw/Fux54hxi -O /bin/sshlimiter

chmod +x /bin/sshlimiter

Digite o comando: "screen" sem as aspas

Dê um enter

Digite o comando: "sshlimiter" sem as aspas

Minimize a screen com o comando: ctrl a + d
```

**Alterar Limite Conexões simultanea Usuario Especifico**
```
wget http://pastebin.com/raw/swAeTx8R -O /bin/alterarlimite

chmod +x /bin/alterarlimite
```

**SSH Monitor**
```
wget http://pastebin.com/raw/ZxYTkGkN -O /bin/sshmonitor

chmod +x /bin/sshmonitor
```

**Logo em seguida para executar o script, digite o nome do mesmo, ex:**

```
addhost
```

>Em "pastebin... coloque o link do script que vocÊ deseja, e /bin/nom

# Proxy ( Squid Completo )

```
nano /etc/squid3/squid.conf
ou
Para Ubuntu 16 execute: nano /etc/squid/squid.conf
```

| Sistema Operacional | Comando |
| :---         |          ---: |
| Debian 7, 8, Ubuntu 14   | nano /etc/squid3/squid.conf    |
| Ubuntu Server 16.04 64bit    | nano /etc/squid/squid.conf      |

> Para baixar o arquivo squid.conf para sua vps, execute o seguinte comando

```
wget http://pastebin.com/raw/mBRLzZhG -O /etc/squid3/squid.conf
ou
Para Ubuntu 16 execute: wget http://pastebin.com/raw/eC3DYsg0 -O /etc/squid/squid.conf
```
```
#IMPEDIR USAR PROXY EM OUTRAS SSH
acl url1 dstdomain -i 127.0.0.1
acl url2 dstdomain -i localhost
acl url3 dstdomain -i DIGITE AQUI O IP DA SUA VPS

#ACESSOS ACLS
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

#NOME DO SERVIDOR
visible_hostname vpsmanager

forwarded_for off
via off
```

# Arquivo Payload.txt

```
nano /etc/squid3/payload.txt
ou
Para Ubuntu 16 execute: nano /etc/squid/payload.txt
```

> Para baixar o arquivo payload para sua vps, execute o seguinte comando

```
wget http://pastebin.com/raw/JFYgf8Hq -O /etc/squid3/payload.txt
ou
Para Ubuntu 16 execute: wget http://pastebin.com/raw/JFYgf8Hq -O /etc/squid/payload.txt
```

```
.claro.com.br
.claro.com.sv
.facebook.net
.netclaro.com.br
.speedtest.net
.tim.com.br
.vivo.com.br
.oi.com.br
.cloudfront.net
.d1n212ccp6ldpw.cloudfront.net
```
