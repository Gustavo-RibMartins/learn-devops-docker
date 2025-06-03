# Introdução ao Docker - Curso de IaC com Terraform

Utilização e configuração do Docker para estudos de Terraform.

---

## 1. Hello World

Executar no terminal:

```docker
docker run hello-world
```

---

## 2. Criando um Servidor Web

```docker
docker run -d -p 8080:80 nginx
```

Comando `-d` coloca o conteiner em execução (running).

Mapeamento de portas `-p`:

* Do lado esquerdo dos dois pontos = porta do host;
* Do lado direito dos dois pontos = porta do conteiner.

---