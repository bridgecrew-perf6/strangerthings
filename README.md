# Boas vindas ao repositório backend do projeto de Deploy - Stranger Things!
veja o deploy em Heruko
https://eduardoputinatti-dw.herokuapp.com/

#### 1 - Verifica as variáveis de ambiente

Altere o backend para utilizar variáveis de ambiente para controlar os seguintes comportamentos:

   1. A porta que a API escutará, essa variável deve ter, nescessariamente, o nome PORT e o seu valor deve ser 3000.

   2. O modo "upsideDown". Essa variável espera um valor boleano e deverá se chamar UPSIDEDOWN_MODE. Lembre-se que as variáveis de ambiente são `strings`.

   O que será testado:
   - Se existe a variável de ambiente PORT.
   - Se a variável de ambiente UPSIDEDOWN_MODE existe e se ela é um boleano.

**Importante**: Para esse projeto, as variáveis de ambiente devem ser definidas em um arquivo .env e o arquivo deve ser enviando no seu PR(Pull Request). ISSO NÃO É UMA PRÁTICA DE MERCADO, o arquivo .env deve ser sempre incluido no .gitignore pois contém informações sensíveis, aqui será enviado apenas por motivo de avaliação.

#### 2 - Verifica se o arquivo Dockerfile está configurado da maneira correta

O teste irá verificar se o arquivo `Dockerfile` existe e está configurado da maneira correta. Ele deve construir a imagem a partir da `node:14-alpine` e usar o comando `npm start` para iniciar a aplicação via `CMD`.

  O que será testado:
  - Se a Dockerfile está utilizando a imagem `node:14-alpine`, verificando se as camadas desta imagem estão incluídas no build que essa Dockerfile faz.
  - Se a Dockerfile usa `npm start` como `CMD`.

#### 3 - Verifica se o arquivo heroku.yml está configurado na maneira correta

Adicione e configure o arquivo `heroku.yml`

  1. O arquivo deve iniciar um servidor do tipo `web`
  2. O `run` deve executar o servidor utilizando o `node`.

Execute ambos em sua máquina para validar se o comportamento é o esperado.

O que será testado:
  - Se o arquivo `heroku.yml` existe.
  - Se o serviço a ser executado é um serviço do tipo `web`.
  - Se o `node` é responsável por executar o servidor.

#### 4 - Verifica action de Linter para ser executada no GitHub

Você deverá criar uma `Action` para ser executada somente em **pull_requests** solicitados em todas as branchs de seu repositório.

**Atenção**: O arquivo de configuração da action deverá ser criado em: `./actions/` com o nome `project.yml`.

O que será testado:
- Se o arquivo `./actions/project.yml` existe.
- Se a `Action` é acionada somente em `pull_request`.
- Se o job foi nomeado como: `eslint`.
- Se o linter está sendo executado com a versão **20.04** do ubuntu.
- Se o linter está sendo executado com a versão 12 do node.

#### 5 - Verifica o Deploy no Heroku

**IMPORTANTE**: Uma variável de ambiente com o nome `GITHUB_USER` deverá ser criada em seu `.env` com o **seu nome de usuário** do GitHub.

**IMPORTANTE :warning:**: O Heroku limita o tamanho do nome de uma aplicação para ter no máximo **30 caracteres**, se o seu nome de usuário do GitHub possuir mais que 27 caracteres você não conseguirá criar uma aplicação com o nome no padrão solicitado pelo requisito. **Caso esteja nessa condição, avise nosso time de instrunção que iremos ajudar**.

1. Crie dois `apps` do Heroku a partir do mesmo código fonte (código da API). O nome do seu app no Heroku deverá conter seu nome de usuário no GitHub seguido de "-up" e "-dw". Por exemplo, se seu nome de usuário no GitHub for "student" seus apps deverão ter os nomes "student-up" e "student-dw" e as URLs abaixo:

   - https://student-up.Herokuapp.com/ - para o app hawkins

   - https://student-dw.Herokuapp.com/ - para o app upside-down

2. Configure a variável de ambiente criada para controlar o modo `UPSIDEDOWN`. Cada um dos `apps` deverá ter valores distintos, da seguinte maneira:

   - O app `hawkins` deverá ter o valor `false`;

   - O app `upside-down` deverá ter o valor `true`.

3. Utilizando o `git`, faça o deploy de ambos os `apps` no Heroku.

Acesse os URLs geradas e valide se ambas as API's estão no ar e funcionando como esperado.

**Importante**: As URLs deverão ser geradas pelo Heroku e não devem ser modificadas.

O que será testado:
  - Se ao fazer uma requisição do tipo GET para o endpoint da API hawkins serão retornadas as informações corretas.
  - Se ao fazer uma requisição do tipo GET para o endpoint da API upside-down serão retornadas as informações corretas.

