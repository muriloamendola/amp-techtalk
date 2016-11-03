# amp-techtalk

Techtalk sobre Google AMP (Accelerated Mobile Pages)

Google - Code Labs

Conceitos básicos: https://codelabs.developers.google.com/codelabs/accelerated-mobile-pages-foundations/index.html?index=..%2F..%2Findex#0

Conceitos Avançados: https://codelabs.developers.google.com/codelabs/accelerated-mobile-pages-advanced/index.html?index=..%2F..%2Findex#0


- O que é e para que serve?

AMP Accelerated Mobile Pages
- É uma iniciativa open source do Google para ajudar os publishers de conteúdo, como nós, a tornar a experiência do usuário no consumo de conteúdo o mais agradável possível e uma premissa para isso é a velocidade no carregamento da página.

Benefícios
- Obviamente além de oferecer uma experiência de consumo mais agradável para nossos usuários, o Google irá privilegiar no mecanismo de busca os publishers que utilizarem essa tecnologia. Inclusive exibindo o conteúdo no carrossel de notícias.
- Uma vez que nosso conteúdo possui uma maior relevância nas buscas, obviamente, teremos uma maior audiência em nossas matérias e isso se reverte em din din se soubermos trabalhar esse usuário em nossos sites.


Características de um código AMP

- Não é necessário que o arquivo possua a extensão .amp ele pode ter qualquer extensão.
É comum em um série de publishers a adoção do seguinte padrão: article.html?amp, ou seja, um parâmetro amp define que o template segue os padrões AMP.

Mão na massa!!!

- Pegar código html simples (colocar no meu github) e transformá-lo em um código AMP

- Adicionar AMP javascript library (checar Chrome console)

- Adicinar fragmento #developer=1 para acionar o validador AMP ao código

- Corrigir os erros apontados pelo validador AMP
  - Adicionar o atributo ⚡ à tag <html> para sinalizar que o documento é um documento AMP.
  - Adicionar meta charset="utf-8"
  - Adicionar link rel="canonical": nada mais é que o link para a matéria original. Caso seja um projeto AMP standalone, ou seja, só possuo a versão AMP da matéria o canonical link deve ser a própria matéria amp.
  - Adicionar a meta tag viewport. Isso já é uma exigência sempre que desenvolvemos html para dispositivos móveis, pois, é essa tag que diz para o browser mobile como nosso html deve ser exibido. Sem essa tag o html é exibido como se fosse para um desktop.

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

  THE END


Best Practices (para que nossas matérias apareçam no carrossel de resultados)

- Link canonical bidirecional (garantir que não são duas matérias falando da mesma coisa)
- Search Engine Meta Data para auxiliar os mecanismos de busca a entender o nosso conteúdo. No AMP temos de adicionar um script no formato application/ld+json na tag head.
        (https://www.ampproject.org/docs/guides/discovery)


Avançado

- amp-ad

<amp-ad
  width="300"
  height="250"
  type="doubleclick"
  data-slot="/35096353/amptesting/image/static">
</amp-ad>

- amp-video

<script async custom-element="amp-youtube" src="https://cdn.ampproject.org/v0/amp-youtube-0.1.js"></script>

<amp-youtube
  data-videoid="mGENRKrdoGY"
  layout="responsive"
  width="480"
  height="270">
  <div fallback>
    <p>The video could not be loaded.</p>
  </div>
</amp-youtube>


- amp-carousel

<script async custom-element="amp-carousel" src="https://cdn.ampproject.org/v0/amp-carousel-0.1.js"></script>

<amp-carousel layout="fixed-height" height="168" type="carousel" >
  <amp-img src="mountains-1.jpg" width="300" height="168"></amp-img>
  <amp-img src="mountains-2.jpg" width="300" height="168"></amp-img>
  <amp-img src="mountains-3.jpg" width="300" height="168"></amp-img>
</amp-carousel>
