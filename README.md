# Sistema de enquetes em realtime

## 📃 Descrição
Esta é um projeto Back-end que cria um API em Node.js ao qual um usuário gerenciar um sistema enquetes através de requisições HTTP e armazenando-os em um banco de dados.

## Sistema de rotas
### POST/polls
O usuário poderá criar uma nova enquete através de uma requisição POST. A API irá salvar esta nova enquete dentro de um banco de dados Postgres.

### GET/polls/:id
O usuário poderá obter detalhes de uma única enquete através de uma rota GET recebendo o id da enquete ao qual ele quer receber os dados. A API irá buscar estes dados no banco de dados.

### POST/polls/:id/votes
O usuário também poderá criar um voto para selecionar qual opção da enquete ele está votando. A API irá salvar este voto no banco de dados.

### WebSocket
Através de um protocolo `ws`, será criada uma comunicação assíncrona e em tempo real entre o usuário e o servidor . A API vai ficar observando toda vez que houver um novo voto na enquete, ela vai avisar a requisição WebSocket que houve um novo voto que será informado ao usuário em tempo real.


## 🛠 Tecnologias
![NodeJS](https://img.shields.io/badge/node.js-6DA55F?style=for-the-badge&logo=node.js&logoColor=white) ![Fastify](https://img.shields.io/badge/fastify-%23000000.svg?style=for-the-badge&logo=fastify&logoColor=white) ![TypeScript](https://img.shields.io/badge/typescript-%23007ACC.svg?style=for-the-badge&logo=typescript&logoColor=white) ![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white) ![Prisma](https://img.shields.io/badge/Prisma-3982CE?style=for-the-badge&logo=Prisma&logoColor=white) ![Postgres](https://img.shields.io/badge/postgres-%23316192.svg?style=for-the-badge&logo=postgresql&logoColor=white) ![Redis](https://img.shields.io/badge/redis-%23DD0031.svg?style=for-the-badge&logo=redis&logoColor=white)

## ⚙ Recursos
`@fastify/websocket` é um plugin que permite adicionar suporte para comunicação bidirecional em tempo real utilizando WebSockets em aplicativos desenvolvidos com Fastify. Com ele é possível monitorar os resultados de um enquete.

`@fastify/cookie` é outro plugin que fornece uma maneira fácil de manipular cookies em aplicativos Fastify.

`ioredis` que é uma biblioteca cliente Node.js que serve para interagir com o Redis, um popular banco de dados em memória. A função do Redis é armazenar a contagem de votos de cada opção para cada enquete.

`zod` que  é uma biblioteca de validação de esquemas para JavaScript e TypeScript. Ele permite definir e validar esquemas de dados de forma fácil e segura, garantindo que seus dados atendam aos critérios especificados.

## 💻 Executando
Após clonar o repositório, acesse a pasta do projeto e execute os comandos abaixo no seu terminal:

```

npm install

```
## Docker Compose
Este projeto utiliza o docker para configurar containers do Postgres e Redis.
Crie um arquivo na parte principal do seu projeto com o nome de `docker-compose.yml` e copie o seguinte código:

![docker-compose](https://imgur.com/YEfttGA.png)

Após isso, execute o seguinte comando no seu terminal para executar o container:

```

docker compose up -d

```

Em seguida, execute no terminal o comando para iniciar o prisma:

```

npx prisma init

```

Com este comando, será criado o arquivo onde serão armazenados as migrações do prisma e também será criado o arquivo `.env` no seu projeto. Neste arquivo `.env` você deve usá-lo para configurar a variável de ambiente para refletir as informações passadas no arquivo de receita do `docker`. Copie este código e adicione ao seu arquivo `.env`.

![env_file](https://imgur.com/GLLkW1D.png)

Execute o seguinte comando para executar o servidor:

```

npm run dev

```

Assim que o projeto estiver rodando, acesse o seu `http://localhost:3333`

## 🙋‍♂️ Colaboradores
Este projeto foi desenvolvido por mim Wilker Guimarães, através do evento NLW-Expert da Rockeseat na trilha de Node.js. Com o objetivo de aplicar os conhecimentos de Node.js para desenvolver um projeto Back-end utilizando os conceitos mais modernos de desenvolvimento e utilização de ferramentas populares.

