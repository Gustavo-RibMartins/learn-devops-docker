# Terraform-AWS Container

Conteiner com terraform instalado para uso com AWS. Possui os seguintes recursos:

* Terraform
* AWS CLI

---

## Criação do conteiner

* Abra o terminal ou prompt de comando e navegue até esta pasta local, em `/learn-devops-docker/imagens/terraform-aws-container/`

* Execute o comando abaixo para criar a imagem docker:

```docker
docker build -t gusribm-terraform-image:lab .
```

* Execute o comando abaixo para criar o container docker

```docker
docker run -dit --name terraform-container gusribm-terraform-image:lab /bin/bash
```

* Verifique as versões do Terraform e do AWS CLI com os comandos abaixo:

```bash
terraform --version
aws --version
```

* Acesse o terminal do conteiner e execute o comando:

```bash
aws configure
```

Informa a access e a secret-key para acessar a AWS de forma programática.