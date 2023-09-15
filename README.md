# Santander Bootcamp 2023 - Fullstack Java+Angular | Digital Innovation One 

## Lab Project 
*Publicando Sua API REST na Nuvem Usando Spring Boot 3, Java 17 e Railway*

**Descrição:** Vamos mergulhar diretamente no universo do desenvolvimento e construir uma API REST do zero! E o melhor de tudo, faremos isso utilizando o Java 17, a versão LTS mais recente que está recheada de novidades empolgantes. Para tornar a nossa jornada ainda mais produtiva, vamos empregar o poder do Spring Boot 3, que é amplamente conhecido por potencializar a produtividade dos desenvolvedores através de sua incrível capacidade de autoconfiguração. Mas não para por aí, vamos simplificar ainda mais o acesso aos bancos de dados SQL com o auxílio do Spring Data JPA. Durante nosso percurso, também vamos tratar da importância de uma documentação de API bem construída e fácil de compreender, para isso, vamos usar o OpenAPI, também conhecido como Swagger. Para finalizar nosso projeto, vamos usar o Railway, uma plataforma que torna o Deploy de soluções na nuvem muito mais simples. Assim, podemos nos concentrar no que realmente importa: o desenvolvimento das nossas soluções!

## Diagrama de classes

```mermaid
classDiagram
  class User {
    -name: String
    -account: Account
    -features: Feature[]
    -card: Card
    -news: News[]

    +getName(): String
    +getAccount(): Account
    +getFeatures(): Feature[]
    +getCard(): Card
    +getNews(): News[]
  }

  class Account {
    -number: String
    -agency: String
    -balance: Float
    -limit: Float

    +getNumber(): String
    +getAgency(): String
    +getBalance(): Float
    +getLimit(): Float
  }

  class Feature {
    -icon: String
    -description: String

    +getIcon(): String
    +getDescription(): String
  }

  class Card {
    -number: String
    -limit: Float

    +getNumber(): String
    +getLimit(): Float
  }

  class News {
    -icon: String
    -description: String

    +getIcon(): String
    +getDescription(): String
  }

  User -- Account : has
  User -- Feature : has
  User -- Card : has
  User -- News : has

```

## Notas
- JSON Editor Online: Para organizar a abstração do layout (ex: Figma) em possíveis entidades.
  - Arquivo: "./drafts/layout-to-abstraction.json"
- ChatGPT: Pegar o .json criado e gerar um diagrama de classes (UML) para o projeto.
  - Prompt: "Gere um diagrama de classes (usando a sintaxe Mermaid) tendo em vista o seguinte JSON que representa um usuário de um banco. Mantenha o idioma das classes em inglês. Mantenha uma estrutura simples e fiel ao modelo que vou passar: [Cole o conteúdo criado no JSON] ."
  - Arquivo: "./drafts/classes-diagram.txt"






