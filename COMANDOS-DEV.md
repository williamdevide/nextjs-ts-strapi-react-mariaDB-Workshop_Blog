Projeto de Blog com Strapi + Postgres + Docker

1. Pasta deve estar vazia

2. Iniciar projeto Strapi
    npx create-strapi-app .
    > Y
    > Custom (manual settings)
    > Javascript
    > postgres
    > [nome-do-banco-de-dados]
    > [ip]
    > [porta]
    > [username]
    > [password]
    > no

3. Rodar o projeto
    npm run develop

4. Criar conta no Cloudinary para upload de imagens e instalar a instância no projeto

    npm install @strapi/provider-upload-cloudinary --save

    criar o arquivo config/plugins.js
    <>
    module.exports = ({ env }) => ({
      // ...
      upload: {
        config: {
          provider: 'cloudinary',
          providerOptions: {
            cloud_name: env('CLOUDINARY_NAME'),
            api_key: env('CLOUDINARY_KEY'),
            api_secret: env('CLOUDINARY_SECRET'),
          },
          actionOptions: {
            upload: {},
            uploadStream: {},
            delete: {},
          },
        },
      },
      // ...
    });
    <>

    preencher no .env (pegar os dados no dashboard do Cloudinary)
    CLOUDINARY_NAME=dxuq2jhxr
    CLOUDINARY_KEY=594495743451616
    CLOUDINARY_SECRET=kE8PTyeTMMCML__jCKa2UJTMxZI
