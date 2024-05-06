# Guia de Uso: Docker Compose para Banco de Dados PostgreSQL

Este guia fornecerá instruções passo a passo para criar e executar um contêiner Docker para subir um banco de dados PostgreSQL usando o Docker Compose.

## Pré-requisitos

Certifique-se de ter o Docker e o Docker Compose instalados em sua máquina. Você pode instalá-los seguindo as instruções oficiais em [Docker](https://docs.docker.com/get-docker/) e [Docker Compose](https://docs.docker.com/compose/install/).

## Passos

1. **Clone este repositório:**
   
   ```bash
   git clone https://github.com/Adptare/DockerFile.git
   ```

2. **Navegue até o diretório do projeto:**
   
   ```bash
   cd adaptare/api/db
   ```

3. **Modifique o arquivo `env_file.env` para configurar as variáveis de ambiente:**
   
   ```bash
   nano env_file.env
   ```

   Edite o arquivo `.env` conforme necessário para definir variáveis como senha do banco de dados, porta, etc.

4. **Inicie o contêiner do Docker Compose:**
   
   ```bash
   docker-compose up --build -d
   ```

   Isso irá criar e iniciar o contêiner Docker para o banco de dados PostgreSQL. O parâmetro `-d` é opcional e significa "detached", o que faz com que o contêiner seja executado em segundo plano.

5. **Verifique se o contêiner está em execução:**
   
   ```bash
   docker ps
   ```

   Você deverá ver o contêiner PostgreSQL em execução na lista.

6. **Acesse o banco de dados via cliente PostgreSQL:**
      
   ```bash
   psql -h localhost -p 5432 -U postgres
   ```

   Você será solicitado a inserir a senha definida no arquivo `.env`.

7. **Execute as operações desejadas no banco de dados.**

8. **Para parar o contêiner Docker:**
   
   ```bash
   docker-compose down
   ```

   Isso irá parar e remover o contêiner do Docker.

## Observações

- Certifique-se de substituir as variáveis de ambiente e configurações conforme necessário no arquivo `.env`.
- Este exemplo usa a porta padrão 5432 para PostgreSQL. Se você precisar alterá-la, atualize-a no arquivo `docker-compose.yml`.
- Lembre-se de que os dados do banco de dados serão persistidos no volume Docker, a menos que você os exclua explicitamente.
- Certifique-se de revisar e ajustar as configurações de segurança e acesso conforme necessário para o seu ambiente específico.
