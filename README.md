### Node with TypeScript

Olá! estou testando o nodejs com typescript!

---

   1. Crie uma pasta e navegue até ela.
   2. Execute os seguintes comando.
      ```
        1. yarn init -y
        2. yarn add typescript -D (Pq dev? o build gerado eh em js)
        3. yarn add express
        4. yarn add @types/express
        5. yarn add ts-node-dev -D (Mais bacana que o nodemon)

      ```
   3. Execute. yarn tsc --init
      1. Ele vai gerar um arquivo tsconfig.json, precisamos edita-lo.
      2. Altere a propriedade outDir e rootDir.
      3. "outDir": "./dist".
      4. "rootDir": "./src".
   4. Vamos no arquivo package.json e adicionamos o script abaixo.
      ```json
        "scripts": {
          "server:dev":"ts-node-dev --transpile-only --inspect --ignore-watch node_modules src/server.ts"
        },
      ```
       O ts-node-dev vai transpilar nosso código e ao mesmo tempo fica ouvindo se tem alguma alteração. A flag --transpileOnly, server para o ts-node-dev não verificar se o código está errado, existe outras ferramentas, --ignore-watch node_modules eh para não ficar ouvindo alterações no node_modules.
    5. Criei na raiz do projeto a pasta src/index.ts, com o código a seguir.
        ```javascript
          import express from 'express';

          const app = express();

          app.get('/', (request, response) => {
            return response.json({ message: 'Hello Edson' });
          });

          app.listen(3333, () => {
            console.log('Server started on port 3333');
          });
        ```
    6. Prontinho, configurado com TS.

