# Usando a imagem oficial do Ubuntu como base
FROM ubuntu:latest

# Mantenedor da imagem 
LABEL maintainer="Gustavo Ribeiro Martins"

# Atualizando os pacotes do sistema e instalar dependências necessárias
RUN apt-get update && \
    apt-get install -y wget unzip curl

# Definir a versão do Terraform 
ENV TERRAFORM_VERSION=1.12.0

# Baixar e instalar Terraform
RUN wget https://releases.hashicorp.com/terraform/${TERRAFORM_VERSION}/terraform_${TERRAFORM_VERSION}_linux_amd64.zip && \
    unzip terraform_${TERRAFORM_VERSION}_linux_amd64.zip && \
    mv terraform /usr/local/bin/ && \
    rm terraform_${TERRAFORM_VERSION}_linux_amd64.zip

# Criar a pasta /lab dentro do container
RUN mkdir /lab

# Copiar main.tf para a pasta /lab no container
COPY main.tf /lab/

# Criar a pasta Downloads e instalar o AWS CLI (para acessar a AWS)
RUN mkdir Downloads && \
    cd Downloads && \
    curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip" && \
    unzip awscliv2.zip && \
    ./aws/install

# Definir o comando padrão para execução quando o container for iniciado
CMD ["/bin/bash"]
