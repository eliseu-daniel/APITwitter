### Passo a passo para rodar o projeto

## Pré-requisitos

Certifique-se de ter as seguintes ferramentas instaladas:

- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)

1. **Clone o projeto**

```bash
git clone https://github.com/eliseu-daniel/APITwitter.git
```

```bash
cd APITwitter
```

2. **Crie o Arquivo .env**

```bash
cp .env.example .env
```

3. **Configure o WWWGROUP e Outras Variáveis**

Verifique e ajuste as variáveis ```WWWGROUP```, ```DB_DATABASE```, ```DB_USERNAME```, ```DB_PASSWORD``` no arquivo .env para garantir que o ambiente Docker esteja corretamente configurado.

4. **Suba os containers do projeto**

```bash 
docker compose up -d --build
```

5. **Acesse o container**

```bash
docker-compose exec laravel.test bash
```

6. **Instale as dependências do projeto**

```bash
composer install
```

7. **Gere a key do projeto Laravel**

```bash
docker compose exec laravel.test php artisan key:generate
```

8. **Execute as Migrations**

```bash
docker compose exec laravel.test php artisan migrate
```

9. **Execute a aplicação**

```bash
./vendor/bin/sail up
```

Após a configuração, a aplicação Laravel estará disponível em ```http://localhost:80/api/```.