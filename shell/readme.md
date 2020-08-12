How create alias on shell

```shell
alias cookbook='cd ~/workspace/cookbook'
```

Remover .DS_Store

```shell
find . -name '.DS_Store' -type f -delete
```

Criar chave ssh associada a um usuário

```shell
ssh-keygen -t rsa -f gcp-helioalb -C helioalb
```

Usando a chave

```shell
ssh -i gcp-helioalb helioalb@<ip da máquina>
```

Adicionar usuário a um grupo

```shell
sudo /usr/sbin/usermod -aG www-data helio
```

Permissão de escrita para grupo

```shell
sudo chmod g+w /var/www/html/
```

Compactar diretório com tar

```shell
tar -czvf name-of-archive.tar.gz /path/to/directory-or-file
```
Fazer diretórios filhos seguirem grupo do diretório pai
