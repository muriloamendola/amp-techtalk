# amp-techtalk
> Projeto construido para techtalk sobre AMP (Accelerated Mobile Pages) -  Editora Globo | InfoGlobo

## AMP (Accelerated Mobile Pages) ⚡ https://www.ampproject.org/

É uma iniciativa open source do Google para distruibuição de conteúdo otimizado para dispositivos móveis, a fim de tornar a experiência do usuário o mais agradável possível.

### Benefícios - publishers

* Carregamento "instantâneo" do conteúdo para gerar engajamento dos usuários
* Possibilidade de ter o conteúdo exposto no novo carrossel de resultados.
* Aumento de audiência proveniente de busca orgânica.
* Google AMP Cache (https://developers.google.com/amp/cache/) - economia de recursos de Infra Estrutura

## Getting started

O propósito desse tutorial é apresentar os conceitos básicos para se criar um documento AMP.

### O que você precisa para realizar esse tutorial

* Baixar o código fonte de exemplo
* Chrome - browser
* Editor de texto de sua preferência. Esse exemplo foi criado com o editor Atom (https://atom.io/)
* Web Server de sua preferência

### Baixando o código fonte de exemplo

```shell
git clone https://github.com/mcamendola/amp-techtalk.git
```

### Rodando a página de exemplo

Os testes serão realizados no Google Chrome e precisamos rodar o nosso código a partir de um Web Server. Nesse tutorial utilizaremos o Chrome 200 OK Web Server, uma extensão do Chrome browser que pode ser instalado a partir da url: https://chrome.google.com/webstore/detail/web-server-for-chrome/ofhbbkphhbklhfoeikjpcbhemlocgigb

Após a instalação do Chrome 200 OK Web Server, certifique-se de que as configurações estejam da seguinte forma:

![alt tag](https://raw.githubusercontent.com/mcamendola/amp-techtalk/master/tutorial/chrome_web_server_configurations.png)

Após configurar o Web Server acesse a seguinte url: http://127.0.0.1:8000/materia.html

## AMP na prática

Vamos criar um novo arquivo chamado materia.amp.html que será a representação ⚡ da matéria original contida no arquivo materia.html.

```shell
ATENÇÃO: Não há nenhuma regra para nomenclatura do documento ⚡. Ele pode ser nomeado de acordo com a preferência de cada publisher.
```

### Criando documento AMP Step-by-step

* Adicionar AMP javascript library (checar Chrome console)
```shell
<script async src="https://cdn.ampproject.org/v0.js"></script>
```
![alt tag](https://raw.githubusercontent.com/mcamendola/amp-techtalk/master/tutorial/amp_js_library.png)

* Adicionar fragmento #development=1 à url para acionar o validador AMP ao código
![alt tag](https://raw.githubusercontent.com/mcamendola/amp-techtalk/master/tutorial/amp_validator.png)

* Adicionar o atributo ⚡ à tag <html> para sinalizar que o documento é um documento AMP.
```shell
<html ⚡ lang="pt-br">
```
![alt tag](https://raw.githubusercontent.com/mcamendola/amp-techtalk/master/tutorial/amp_tag_html.png)

* Adicionar meta charset="utf-8"
```shell
<meta charset="utf-8" />
```
![alt tag](https://raw.githubusercontent.com/mcamendola/amp-techtalk/master/tutorial/meta_charset_utf8.png)

* Adicionar 'link rel=canonical' que corresponde à referência, link, para a matéria original (no caso materia.html).
```shell
<link rel="canonical" href="/materia.html">
```
![alt tag](https://raw.githubusercontent.com/mcamendola/amp-techtalk/master/tutorial/link_rel_canonical.png)

* Adicionar a meta tag viewport. Isso já é uma exigência sempre que desenvolvemos html para dispositivos móveis, pois, é essa tag que diz para o browser mobile como nosso html deve ser exibido. Sem essa tag o html é exibido como se fosse para um desktop.
```shell
<meta name="viewport" content="width=device-width,minimum-scale=1,initial-scale=1">
```
![alt tag](https://raw.githubusercontent.com/mcamendola/amp-techtalk/master/tutorial/meta_viewport.png)

  - css externo não é permitido. O propósito do AMP é oferecer uma experiência agradável para o usuário e um ponto importante para que isso seja possível é a performance. O carregamento da matéria deve ser rápido, então, não é permitido a inclusão de um css externo, o css deve ser inline no próprio html.
     (Atenção para o tamanho máximo permitido de 50KB - sugestão é utilizar minificadores de css)
     (Apenas uma tag style amp-custom é permitida)

  - javascript: diferente do css que facilmente pudemos remover a referencia para o arquivo externo e adicionarmos o código inline, para javascript o AMP é um pouco mais restrito e possui três regras básicas de utilização:
    - Todo javascript deve ser assincrono (possuir o atributo async na tag script)
    - AMP javascript library and AMP components (https://www.ampproject.org/docs/reference/components) podem ser adicionados ao seu código
    - Podemos incluir javascript de terceiros a partir da utilização de iframes, mas, essa prática é totalmente desencorajada pelo Google. O ideal é utilizar os AMP components

  - amp-boilerplate: Ainda na linha de melhorar a experiência do usuário quando estiver consumindo o conteúdo o AMP quer garantir que o contéudo só será visível para o usuário uma vez que o carregamento da página estiver completo e todos os componentes estejam estilizados. Para isso adicionamos a tag style amp-boilerplate.
    - a tag noscript garante o funcionamento caso o javascript do browser esteja desativado.

  - subistituição da tag img pelo component amp-img
    - o componente diferente da tag img exige que informemos os atributos width e height da imagem. Isso ajuda o AMP a definir o aspect ratio da mesma e consequentemente ajustá-la de acordo com o device que está acessando (tamanho da tela).
    - A exigência em informar o width e o height tem um propósito. Denovo, para melhorar a performance se informamos o width e o height do elemento evitamos o chamado DOM reflow durante o processo de renderização da página. O DOM reflow é o processo de identificação das características do elemento para então renderizá-lo e isso é muito custozo para o browser uma vez que ele pode ser executado de forma recursiva inúmeras vezes.


## Referências

### Google - Code Labs
* Conceitos básicos: https://codelabs.developers.google.com/codelabs/accelerated-mobile-pages-foundations/index.html?index=..%2F..%2Findex#0
* Conceitos Avançados: https://codelabs.developers.google.com/codelabs/accelerated-mobile-pages-advanced/index.html?index=..%2F..%2Findex#0
