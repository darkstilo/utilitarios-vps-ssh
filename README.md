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

# Proxy Baseado no squid


| Sistema Operacional | Comando |
| :---:         |          :---: |
| Debian 7, 8, Ubuntu 14   | nano /etc/squid3/squid.conf    |
| Ubuntu Server 16.04 64bit    | nano /etc/squid/squid.conf      |

> Para baixar o arquivo squid.conf para sua vps, execute o seguinte comando

| Sistema Operacional | Comando |
| :---:         |          :---: |
| Debian 7, 8, Ubuntu 14   | wget http://pastebin.com/raw/mBRLzZhG -O /etc/squid3/squid.conf    |
| Ubuntu Server 16.04 64bit    | wget http://pastebin.com/raw/eC3DYsg0 -O /etc/squid/squid.conf      |


# Arquivo Payload.txt

| Sistema Operacional | Comando |
| :---:         |          :---: |
| Debian 7, 8, Ubuntu 14   | nano /etc/squid3/payload.txt    |
| Ubuntu Server 16.04 64bit    | nano /etc/squid/payload.txt      |

> Para baixar o arquivo squid.conf na sua vps, execute o seguinte comando

| Sistema Operacional | Comando |
| :---:         |          :---: |
| Debian 7, 8, Ubuntu 14   | wget http://pastebin.com/raw/JFYgf8Hq -O /etc/squid3/payload.txt    |
| Ubuntu Server 16.04 64bit    | wget http://pastebin.com/raw/JFYgf8Hq -O /etc/squid/payload.txt      |


# Bloquear Torrent na Rede

> Vou logo avisando que bloquear torrent não é uma tarefa tão simples, já que essa forma de download usa-se várias portas distintas, ou seja, você nunca irá advinhra qual a porta a pessoa poderá utilizar, no entanto, há como deixar isso mais dificil para usuários que tentarem baixa-los da forma normal.

> Para isso baixe o seguinte arquivo bloq na sua vps, execute o seguinte comando

| Sistema Operacional | Comando |
| :---:         |          :---: |
| Debian 7, 8, Ubuntu 14   | wget http://pastebin.com/raw/nvvh0RDy -O /etc/squid3/bloq    |
| Ubuntu Server 16.04 64bit    | wget http://pastebin.com/raw/nvvh0RDy -O /etc/squid/bloq      |
