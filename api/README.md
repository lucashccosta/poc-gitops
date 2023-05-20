# GitOps - API

Rest API utilizada para o estudo do GitOps.

# Rodando a aplicação

Execute no terminal os comandos abaixo:

```sh
# cria a imagem docker
docker build -t poc-gitops-api:latest .
```

```sh
# roda container utilizando a imagem criada
docker run -p 8080:8080 --name poc-gitops-api poc-gitops-api:latest
```

Acesse o navegador ou um cliente Rest e informe a URL:

```sh
http://localhost:8080/api/v1/health
```

# Rest API
## Métodos
Requisições para a API devem seguir os padrões:
| Método | Descrição |
|---|---|
| `GET` | Utilizado para recuperar um registro. |

## Respostas

| Código | Descrição |
|---|---|
| `200` | Requisição executada com sucesso (success).|

### Visualizar Status da Aplicação
+ Endpoint: [GET] http://localhost:8080/api/v1/health
+ Request (application/json)
+ Response (application/json)
    + Body
        ```json
            {
                "srv": "gitops-api",
                "status": "OK",
                "statusHttp": 200
            }
        ```