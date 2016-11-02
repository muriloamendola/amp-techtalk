# amp-techtalk
> Projeto construido para techtalk sobre AMP (Accelerated Mobile Pages) -  Editora Globo | InfoGlobo

## AMP (Accelerated Mobile Pages)

É uma iniciativa open source do Google para distruibuição de conteúdo otimizado para dispositivos móveis, a fim de tornar a experiência do usuário o mais agradável possível.

### Benefícios - publishers

* Obviamente além de oferecer uma experiência de consumo mais agradável para os usuários, o Google irá privilegiar, nos resultados das buscas, os publishers que utilizarem essa tecnologia.
* Possibilidade de ter o conteúdo exposto no novo carrossel de resultados.
* Aumento de audiência proveniente de busca orgânica.

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

![alt tag](http://url/to/img.png)

O diretório do Web Server deve ser o diretório do código fonte de exemplo.

Após configurar o Web Server acesse a seguinte url: http://127.0.0.1:8000/materia.html






Here you should say what actually happens when you execute the code above.

## Developing

Here's a brief intro about what a developer must do in order to start developing
the project further:

```shell
git clone https://github.com/your/awesome-project.git
cd awesome-project/
packagemanager install
```

And state what happens step-by-step.

### Building

If your project needs some additional steps for the developer to build the
project after some code changes, state them here:

```shell
./configure
make
make install
```

Here again you should state what actually happens when the code above gets
executed.

### Deploying / Publishing

In case there's some step you have to take that publishes this project to a
server, this is the right time to state it.

```shell
packagemanager deploy awesome-project -s server.com -u username -p password
```

And again you'd need to tell what the previous code actually does.

## Features

What's all the bells and whistles this project can perform?
* What's the main functionality
* You can also do another thing
* If you get really randy, you can even do this

## Configuration

Here you should write what are all of the configurations a user can enter when
using the project.

#### Argument 1
Type: `String`  
Default: `'default value'`

State what an argument does and how you can use it. If needed, you can provide
an example below.

Example:
```bash
awesome-project "Some other value"  # Prints "You're nailing this readme!"
```

#### Argument 2
Type: `Number|Boolean`  
Default: 100

Copy-paste as many of these as you need.

## Contributing

When you publish something open source, one of the greatest motivations is that
anyone can just jump in and start contributing to your project.

These paragraphs are meant to welcome those kind souls to feel that they are
needed. You should state something like:

"If you'd like to contribute, please fork the repository and use a feature
branch. Pull requests are warmly welcome."

If there's anything else the developer needs to know (e.g. the code style
guide), you should link it here. If there's a lot of things to take into
consideration, it is common to separate this section to its own file called
`CONTRIBUTING.md` (or similar). If so, you should say that it exists here.

## Licensing

One really important part: Give your project a proper license. Here you should
state what the license is and how to find the text version of the license.
Something like:

"The code in this project is licensed under MIT license."
