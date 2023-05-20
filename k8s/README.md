# GitOps - K8s

Arquivos para deploy da aplicação no Kubernetes. Para rodar num cluster K8s, rode o comando:

```sh
kubectl apply -f k8s/ 
```

## api.yml

Arquivo contendo as diretrizes para deploy da aplicação (kind: deployment e service).

## kustomization.yml

Arquivo do plugin [kustomize.io](https://kustomize.io/) que permite atualizar a versão da imagem Docker de forma 
dinâmica, de acordo com o processo de CI/CD (GitHub Actions) - refere-se ao atributo: 

```sh
# api.yml
kind: Deployment > spec.template.spec.containers["gitops-api"].image
```

Para visualizar o funcionamento do kustomize.io, rode o comando e verifique que o campo `images.newTag` é alterado para
`v1.0.0`.

```sh
# api.yml
kustomize edit set image docker-image-gitops-api=poc-gitops-api:v1.0.0
```

