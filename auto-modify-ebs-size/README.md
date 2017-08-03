# auto-modify-ebs-size
Verifica o percentual de uso do device/EBS, se necessário realiza automaticamente o incremento do EBS e realiza o
redimensionamento do file system no Linux, contempla EXT4 e XFS.

Somente apresenta funcionamento com EBS atachados sem partição, exemplo, não funcionará com partição `root /dev/xvda1` somente
com `/dev/xvdb`

## Configuração
* Copie o script para /usr/local/sbin/auto-modify-ebs-size
* O script pode ser executado com `auto-modify-ebs-size /dev/xvdb`
### Exemplo CRON
```
SHELL=/bin/sh
PATH=/usr/local/sbin:/usr/local/bin:/sbin:/bin:/usr/sbin:/usr/bin
15 * * * * root auto-modify-ebs-size /dev/xvdb
```
