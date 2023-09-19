# Universo das Páginas um blog utilizando Jekyll
[![Deploy Jekyll site to Pages](https://github.com/el1ziane/el1ziane.github.io/actions/workflows/jekyll.yml/badge.svg)](https://github.com/el1ziane/el1ziane.github.io/actions/workflows/jekyll.yml)

## Sobre o trabalho:
Para este trabalho foi utilizada a jamstack jekyll, com o objetivo de criar um site estático, como um blog, e adotar os principios de gerência de configuração para implementa-lo.

## Criação e clonagem do repositório:
Este repósitorio foi criado utilizando o inicio rápido do github pages, que consiste em utilizar o domínio `.github.io` após o nome de usuário.
![img0](https://github.com/el1ziane/el1ziane.github.io/assets/113150368/98997dd1-0a24-455e-9b14-e41084f2354e)

Repositório criado! Agora será nessessário clona-lo e traze-lo para o ambiente de desenvolvimento.
Para isso foi preciso escolher um diretório e digitar o seguinte comando:
```
git clone https://github.com/el1ziane/el1ziane.github.io.git
```
Entrar no diretório que foi clonado:
```
cd el1ziane.github.io
```
###### Obs: para proseguir é necessário que tenha os pré requisitos instalados, eles podem ser encontrados [aqui.](https://jekyllrb.com/docs/installation/)
Antes de iniciar o projeto é nessessário instalar as gemas Jekyll e Bundler:
```
gem install jekyll bundler
```
Inicializando o projeto jekyll no repositório:
```
jekyll new . --force
```
E depois:
```
code .
```
Agora é só desenvolver a estrutura inicial do site.

## GitHub Actions:

O GitHub Actions é uma plataforma de automação de fluxos de trabalho integrada ao GitHub, permitindo automatizar tarefas como construir, testar e implantar código.
Os fluxos de trabalho são executados através de máquinas virtuais.

###### Trabalhos: conjunto de etapas executadas em um fluxo de trabalho.

**Fluxos de trabalho**: são definidos por um arquivo `.yaml` no diretório `.github/workflows`, esse arquivo será acionado quando um evento predefinido ocorrer.
###### *Criação do arquivo*: criar um arquivo de configuração YAML chamado `.github/workflows/nome-do-fluxo.yml` no repositório do GitHub. Esse arquivo contém as instruções para o GitHub Actions sobre como executar o fluxo de trabalho.

**Execução**: Quando um evento desencadeador ocorre, o GitHub Actions inicia automaticamente o fluxo de trabalho, seguindo as etapas definidas no arquivo de configuração.
###### Exemplos de eventos:  criar uma solicitação de pull request, abrir um problema ou fazer envio por push de um commit para um repositório.

**Ação**: Dentro do ambiente de execução, utiliza se uma ação (um conjunto de comandos pré-definidos) para construir o site. Por exemplo, na construção de um site estático com Jekyll, utiliza-se uma ação específica para Jekyll.

**Ação de Teste**: Após a construção do site, é possivel adicionar uma ação de teste que verifica se o site foi construído corretamente e se ele atende aos padrões de qualidade definidos. 

**Implantação Automática**: Configurar o ambiente de implantação, que pode ser um servidor de hospedagem, como o GitHub Pages. Dentro do ambiente de implantação, utiliza-se uma ação para implantar o site. Essa ação pode enviar os arquivos gerados durante a construção para o servidor do GitHub Pages.

## Desafios:

**Arquivo de configuração** `.gitignore`:
Por estar utilizando Jekyll com `bundler`, foi necessário seguir a documentação do Jekyll e adicionar os seguintes arquivos ao `.gitignore`:
```
_site
.sass-cache
.jekyll-cache
.jekyll-metadata
vendor
.bundle/
```
###### Obs: a documentação citada pode ser encontrada [aqui.](https://jekyllrb.com/tutorials/using-jekyll-with-bundler/)

**Branch Protegida**

![img2](https://github.com/el1ziane/el1ziane.github.io/assets/113150368/675dbb95-c5e5-4fa4-b034-552f8475961f)

Indo até `⚙️settings` e depois em criar uma nova regra foram selecionadas as seguintes configurações:

![Captura de tela 2023-09-18 213840](https://github.com/el1ziane/el1ziane.github.io/assets/113150368/ed858b1c-586e-4d48-b5d1-f395bbe9752e)  

Brach protegida!

![Captura de tela 2023-09-17 092013](https://github.com/el1ziane/el1ziane.github.io/assets/113150368/98b2e412-3d2b-4e14-b151-ea83a987414f)
Quando alguém tenta fazer um push que não atende às condições estabelecidas nas regras de proteção, o GitHub normalmente impede o push e exibe uma mensagem de erro.
No entanto, ao realizar um push para o brach principal houve a seguinte saida:
```
remote: Bypassed rule violations for refs/heads/main:
```
A mensagem indica que esse push violou alguma das regras de proteção configuradas para o branch. No entanto, o Git permitiu o contorno dessas regras. Isso geralmente acontece quando o autor do push tem permissões especiais, como acesso de administrador ou proprietário do repositório.

**Configuração de Badge**

