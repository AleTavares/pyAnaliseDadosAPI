# Consumindo API e tratando dados com Python

**APIs REST**

Uma API (application programming interface) é uma especificação que define como componentes de software devem interagir entre si (thanks, wikipedia!). APIs REST se utilizam do protocolo HTTP para fornecer determinadas funcionalidades aos seus clientes. Essas funcionalidades são descritas por conjuntos de recursos que podem ser acessados remotamente pelos clientes do serviço, através de requisições HTTP comuns.

Em uma API REST existem dois conceitos principais: os recursos (resources) e as coleções (collections). Um recurso é uma unidade que representa um objeto (composto por dados, relacionamentos com outros recursos e métodos). Já uma coleção é um conjunto de recursos que pode ser obtido acessando uma URL. Tal coleção poderia representar a coleção de todos os registros de determinado tipo, ou então, todos os registros que possuem relacionamento com determinado objeto, ou todos os registros que atendem à determinada condição, etc.

Como você pôde ver, uma API REST nada mais é do que um serviço que fornece acesso remoto a recursos via HTTP. Para podermos entender melhor e fazer requisições HTTP a um serviço REST, precisamos conhecer um pouquinho mais sobre o protocolo HTTP e como seus métodos são utilizados em uma API REST.



**HTTP e seus métodos**

O protocolo HTTP define que uma requisição de um cliente para um servidor é composta por:

Uma linha descrevendo a requisição, composta por:
Método: indica o que desejamos fazer com o recurso. Pode ser: GET, POST, PUT, DELETE, além de outros menos utilizados.
URL: o endereço do recurso que se deseja acessar.
Versão: a versão do protocolo a ser usada.
O corpo da requisição, que pode conter informações como o nome do host de onde desejamos obter o recurso solicitado, dados a serem enviados do cliente para o servidor, etc.

O método de uma requisição HTTP indica a ação que pretendemos realizar com aquela requisição, e cada método tem um significado próprio:

**GET:** utilizado para a obtenção de dados. É o tipo de requisição que o navegador faz a um servidor quando você digita uma URL ou clica em um link.

**POST:** utilizada na web para o envio de dados do navegador para o servidor, principalmente quando esses dados vão gerar alguma alteração no último.
PUT: serve para solicitar a criação de objetos no servidor caso esses ainda não existirem. Na prática, a maioria das páginas utiliza o método POST para isso também.

**DELETE:** serve para indicar que o usuário (emissor da requisição em questão) deseja apagar determinado recurso do servidor.

Após executar a requisição do cliente, o serviço responde com uma mensagem de resposta HTTP. O protocolo HTTP define que as mensagens de resposta devem possuir um campo indicando o status da requisição. O status mais conhecido na web é o 404 (not found – recurso não encontrado), mas existem vários, como: 200 (OK), 401 (not authorized – indicando falta de autenticação), 500 (internal server error – erro no servidor), dentre outros. Por ser baseado em HTTP, o padrão REST define que as mensagens de resposta devem conter um código de status, para que o cliente do serviço web possa verificar o que aconteceu com a sua requisição.

**O quê vamos fazer:**

Acessar uma API do site https://brasil.io e pegarmos dados do Covid-19 e prepararmos estes dados para um futuro enriquecimento.

Para esta tarefa utilizaremos algumas bibliotecas do Python, são elas:
- **Json:**
A biblioteca json disponível no Python pode operar com objetos json originários de arquivos ou strings. Ao decodificar o objeto , a biblioteca o  converte para listas ou dicionários Python. E também o inverso, ou seja, converte listas ou dicionários Python em objetos json.

- **Requests:**
A biblioteca requests é utilizada para fazer solicitações HTTP em Python. Ele abstrai as complexidades de fazer solicitações por trás de uma API simples e bonita, para que você possa se concentrar na interação com os serviços e no consumo de dados em seu aplicativo.

- **Pandas:**
O pandas é uma biblioteca de análise e manipulação de dados de código aberto, rápida, poderosa, flexível e fácil de usar, construída sobre a linguagem Python .
