# Santander Bootcamp 2023 - Fullstack Java+Angular | Digital Innovation One 

## Lab Project 
*Publicando Sua API REST na Nuvem Usando Spring Boot 3, Java 17 e Railway*

**Descrição:** Vamos mergulhar diretamente no universo do desenvolvimento e construir uma API REST do zero! E o melhor de tudo, faremos isso utilizando o Java 17, a versão LTS mais recente que está recheada de novidades empolgantes. Para tornar a nossa jornada ainda mais produtiva, vamos empregar o poder do Spring Boot 3, que é amplamente conhecido por potencializar a produtividade dos desenvolvedores através de sua incrível capacidade de autoconfiguração. Mas não para por aí, vamos simplificar ainda mais o acesso aos bancos de dados SQL com o auxílio do Spring Data JPA. Durante nosso percurso, também vamos tratar da importância de uma documentação de API bem construída e fácil de compreender, para isso, vamos usar o OpenAPI, também conhecido como Swagger. Para finalizar nosso projeto, vamos usar o Railway, uma plataforma que torna o Deploy de soluções na nuvem muito mais simples. Assim, podemos nos concentrar no que realmente importa: o desenvolvimento das nossas soluções!

## Principais Tecnologias
 - **Java 17**: Utilizaremos a versão LTS mais recente do Java para tirar vantagem das últimas inovações que essa linguagem robusta e amplamente utilizada oferece;
 - **Spring Boot 3**: Trabalharemos com a mais nova versão do Spring Boot, que maximiza a produtividade do desenvolvedor por meio de sua poderosa premissa de autoconfiguração;
 - **Spring Data JPA**: Exploraremos como essa ferramenta pode simplificar nossa camada de acesso aos dados, facilitando a integração com bancos de dados SQL;
 - **OpenAPI (Swagger)**: Vamos criar uma documentação de API eficaz e fácil de entender usando a OpenAPI (Swagger), perfeitamente alinhada com a alta produtividade que o Spring Boot oferece;
 - **Railway**: facilita o deploy e monitoramento de nossas soluções na nuvem, além de oferecer diversos bancos de dados como serviço e pipelines de CI/CD.

## Layout
![Layout da aplicação web](./drafts/screenshots/layout-web.png)
### [Link do Figma](https://www.figma.com/file/0ZsjwjsYlYd3timxqMWlbj/SANTANDER---Projeto-Web%2FMobile?type=design&node-id=1421-432&mode=design)

## Diagrama de classes (Domínio da API)
```mermaid
classDiagram
  class User {
    -String name
    -Account account
    -Feature[] features
    -Card card
    -News[] news
  }

  class Account {
    -String number
    -String agency
    -Number balance
    -Number limit
  }

  class Feature {
    -String icon
    -String description
  }

  class Card {
    -String number
    -Number limit
  }

  class News {
    -String icon
    -String description
  }

  User "1" *-- "1" Account
  User "1" *-- "N" Feature
  User "1" *-- "1" Card
  User "1" *-- "N" News
```

## Notas
- [JSON Editor Online](https://jsoneditoronline.org/): Para organizar a abstração do layout (ex: Figma) em possíveis entidades.
  - Arquivo: "./drafts/layout-to-abstraction.json"
- [ChatGPT](https://chat.openai.com/): Pegar o .json criado e gerar um diagrama de classes (UML) para o projeto.
  - Prompt: "Gere um diagrama de classes (usando a sintaxe Mermaid) tendo em vista o seguinte JSON que representa um usuário de um banco. Mantenha o idioma das classes em inglês. Mantenha uma estrutura simples e fiel ao modelo que vou passar: [Cole o conteúdo criado no JSON] ."
  - Arquivo: "./drafts/classes-diagram.txt"
- [OpenAPI Swagger](https://github.com/springdoc/springdoc-openapi): [https://github.com/springdoc/springdoc-openapi](https://github.com/springdoc/springdoc-openapi)

## Local Server (Tomcat)
- API - localhost:8080 
- H2 web interface - localhost:8080/h2-console 
- Swagger - localhost:8080/swagger-ui.html

## Production Server (Railway)
- [Railway](https://railway.app/): [https://railway.app/](https://railway.app/)
- GitHub Integrado do Repositorio para Deploy
- Atualmente fornece $5 dólares mensais para teste dos serviços no Trial Plan
- Deploy:
  - New Project -> Postgres -> criar novo application.yml com as configurações de produção com as config. do banco -> Na IDE, criar perfil de execução com Environment variables -> Na primeira execução, nas config do jpa, deixe o ddl-auto: create -> Execute em modo de produção -> Verifique a execução no console, veja se rodou corretamente, se tive alguns logs de skip, podem significar a criação das tabelas no banco, verifique no dashboard do railway, na aba de Data, as tabelas devem estar listadas -> Pare a execução e volte o valor para a ddl-auto: validate -> Execute novamente em modo de produção, desta vez teremos muito menos warnings -> No Swagger UI crie novos registros -> Agora os dados devem estar persistidos no banco de produção.
  - Para deploy da aplicação prepare os arquivos:
    - build.gradle: para add a Classe principal
    - criar o Procfile: para gerar o jar da build: "web: java -jar  build/libs/santander-dev-week-2023-0.0.1-SNAPSHOT.jar"
    - gradle-wrapper.properties: coloque uma versão do gradle suportada pelo railway, altere a versão no distributionUrl ex: "distributionUrl=https\://services.gradle.org/distributions/gradle-7.6.1-bin.zip"




