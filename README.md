# Projeto: Deploy de Aplicação com CI/CD

Este projeto tem como objetivo implantar uma aplicação simples em uma plataforma cloud com integração de CI/CD.

## Descrição

Como nenhum dos templates do hackathon atendia aos requisitos deste projeto, optei por desenvolver uma API em Python utilizando o framework [Flask](https://flask.palletsprojects.com/en/stable/). A aplicação possui uma única rota voltada para o health check do Kubernetes.

## Desenvolvimento Local

Seguindo boas práticas de DevOps, antes de realizar o deploy na nuvem, a aplicação foi testada localmente em um cluster [Kind](https://kind.sigs.k8s.io/), com a criação dos seguintes recursos:

- **Deployment**
- **Service**
- **Ingress**

Para facilitar a inicialização e testes locais, foi incluído um arquivo `Makefile` com os comandos necessários para subir o ambiente.

## Plataforma Cloud

A plataforma escolhida para o deploy foi a **[Northflank](https://northflank.com/)**, que oferece um plano gratuito ideal para testes e demonstrações.

## Rodar o projeto localmente

``` bash
make dev
```

[Acessar localmente a aplicação](http://flask.local:30080/health)

## Avisos para revisão de código

1. O repositório público ECR da AWS já foi deletado para não gerar custos e não está acessível;
2. A infraestrututura do NorthFlank também já foi deletada, com a mesma justificativa, não gerar custos.

## Checar logs do nginx localmente

``` bash
kubectl get po
kubectl logs <nome_da_pod_do_nginx>
```
