---
title: 'Definindo O Preço De Produtos Com Redes Neurais Artificais'
---

Atualmente, divido o foco dos meus estudos em alguns assuntos (sim, o foco não é tão focado assim): Basicamente Typescript e a certificação para developer da AWS (não vou falar sobre meu tcc nesse momento).

Em Typescript, estou fazendo alguns experimentos com o framework [Nest](https://github.com/nestjs/nest){:target="_blank"}, diferente do express que atua mais como um middleware, o Nest apresenta uma estrutura completa e robusta, já trazendo configurando por default testes com Jest e permitindo o uso de patterns como injeção de dependência, enfim, pretendo fazer um post mais elaborado no futuro sobre o Nest. 

Quanto a certificação da AWS, tenho uma lista de assuntos a qual pretendo fazer algumas implementações e experimentos para fins de fixão do conhecimento. Este primeiro experimento foi desenvolvido usando Nest e o serviço de autenticação da AWS chamado [Cognito](https://aws.amazon.com/pt/cognito/){:target="_blank"}. O Cognito é um poderoso serviço da AWS que permite cadastro e autenticação de usuários, provendo controle de acesso e de fácil integração com outros serviços da AWS.

Não vou entrar nos detalhes da criação do projeto no Nest, mas vou elencar os passos seguidos para configuração do serviço e integração com o código:

1) Configuração do Pull de usuários no Cognito

2) Adição das lib´s necessárias no Nest.

npm install  amazon-cognito-identity-js

3) Criar os arquivos

/src/auth/auth.config.ts
/src/auth/auth.controller.ts
/src/auth/auth.module.ts
/auth.service.ts

4) Alterar o arquivo /src/main.ts