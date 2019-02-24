# GCP

## Compute engine
Listar instâncias

```shell
gcloud compute instances list
```

Acessar instância do compute-engine

```shell
gcloud compute ssh instance-1
```

Parar instância

```shell
gcloud compute instances stop instance-1
```

Criar imagem

```shell
gcloud compute images create site-producao --source-disk instance-1
```

Listar imagens

```shell
gcloud compute images list
```

## Google storage

Listar buckets

```shell
gsutil ls
```

Copiar conteúdo para o bucket

```shell
gsutil -m cp -r imagens/ gs://curso-compute-engine/imagens
```

Remover arquivo

```shell
gsutil rm gs://curso-compute-engine/html/LICENSE
```

Mudar permissão de um diretório para Leitura(R)

```shell
gsutil -m acl -r ch -u AllUsers:R gs://curso-compute-engine/imagens
```

Atualizar somente arquivos com mudança

```shell
gsutil -m rsync -r site-compute-engine-alura/ gs://curso-compute-engine/
```
