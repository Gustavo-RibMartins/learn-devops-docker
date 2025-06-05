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

## 3. Customizando a criação de um Banco de Dados

```docker
docker run --name database -p 5435:5432 -e POSTGRES_USER=dsa -e POSTGRES_PASSWORD=dsa1010 -e POSTGRES_DB=dsadb -d postgres:16.0
```

* `--name`: nome do conteiner
* `-e`: environmet variable
* `-d`: detached
* `postgre:16.0`: versão 16.0 do PostgreSQL

---

## 4. Usando Dockerfile

* Crie um arquivo chamado `Dockerfile` e coloque o conteúdo abaixo:

```dockerfile
FROM python:3.11-slim
COPY testedsa.py /testedsa.py
CMD ["python", "/testedsa.py"]
```

> * `FROM python:3.11-slim`: utiliza a imagem `python:3.11-slim` como template/chassi
> * `COPY testedsa.py /testedsa.py`: copia o arquivo `testedsa.py` para o local `/testedsa.py` no container
> * `CMD ["python", "/testedsa.py"]`: executa no CMD o comando `python /testedsa.py` para rodar o script no conteiner

* Crie um arquivo chamado `testedsa.py` com o seguinte conteúdo:

```python
print("Olá, Bem-Vindo(a) ao Docker com DAS!")
```

* Agora, construa a imagem:

```docker
docker build -t dsa-image .
```

* Execute o conteiner:

```docker
docker run --name dsacontainer dsa-image
```