# stress-ng

Usado para testar cargas

Instalação

```shell
sudo apt-get install stress-ng
```

Load de 90% para 1 cpu durante 5 minutos

```shell
stress-ng -c 1 -l 90 -t 5m
```
