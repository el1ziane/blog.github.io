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

Neste repositório estão presente os seguintes fluxos de trabalho:

![image](https://github.com/el1ziane/el1ziane.github.io/assets/113150368/7960e97e-2bb0-4fa1-aa39-4faf2d935a2e)

Como é possível observar a baixo, o fluxo de trabalho do Jekyll Constroi e implanta automaticamente, de acordo com o cumprimento dos padrões pré estabelecidos:

![Captura de tela 2023-09-18 224042](https://github.com/el1ziane/el1ziane.github.io/assets/113150368/e7eb088c-a4b4-4787-ba2f-0fffdfbf1080)

![Captura de tela 2023-09-18 231006](https://github.com/el1ziane/el1ziane.github.io/assets/113150368/b5b9e2d1-708c-45a3-b311-981e8be79aa1)


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

Criando uma badge de status. Como é possível ver, ao selecionar o fluxo de trabalho basta copiar o link, observe que neste fluxo ocorre um erro no build e no deploy.

![Captura de tela 2023-09-18 231208](https://github.com/el1ziane/el1ziane.github.io/assets/113150368/d2328ac5-01d9-42c7-b4f8-a423e89f51dc)

Após realizar as correções necessárias o status é atualizado automaticamente no `README.md`:

![Captura de tela 2023-09-18 232035](https://github.com/el1ziane/el1ziane.github.io/assets/113150368/4eaf0f8f-903f-46be-8b99-a9f6c11babec)

**Rebase Interativo**

Utilizando o `Git log ` do Git para explorar o histórico do repositório:

![Captura de tela 2023-09-17 143245](https://github.com/el1ziane/el1ziane.github.io/assets/113150368/0526825f-dabf-4c1e-add3-a266e8460fab)

Especificando o intervalo de commits a serem modificados. Nesse caso, para modificar qualquer um dos últimos 3 commits:

```
git rebase --interactive HEAD~3
```

![Captura de tela 2023-09-17 144246](https://github.com/el1ziane/el1ziane.github.io/assets/113150368/7f20fe87-3fc6-4d84-9ea6-f73faafecc4e)

Utilizando `squash` para comprimir dois commits em um e reword para reescrever a mensagem de um commit.

![Captura de tela 2023-09-17 150957](https://github.com/el1ziane/el1ziane.github.io/assets/113150368/53406abb-edaf-4547-86cf-ddaacfb16a92)

Reescrevendo a mensagem do primeiro commit.

Após o rebase é possivel observar que dois commits foram convertidos em 1 e que a mensagem foi reescrita:

![Captura de tela 2023-09-17 151055](https://github.com/el1ziane/el1ziane.github.io/assets/113150368/92023fad-957d-47dc-8944-427eae173d50)

![Captura de tela 2023-09-17 151244](https://github.com/el1ziane/el1ziane.github.io/assets/113150368/777e4650-a0e2-4b76-ad7c-7dc3ad64cd61)


![Captura de tela 2023-09-17 122513](https://github.com/el1ziane/el1ziane.github.io/assets/113150368/4edfb6a7-1f70-4666-b73b-a38f07b92153)

![Captura de tela 2023-09-17 103643](https://github.com/el1ziane/el1ziane.github.io/assets/113150368/e96d3da4-f035-4a26-93e2-7627df76c645)

![Captura de tela 2023-09-17 103643](https://github.com/el1ziane/el1ziane.github.io/assets/113150368/1ddd3220-c635-462c-a224-196dbbb234d8)


![Captura de tela 2023-09-17 095553](https://github.com/el1ziane/el1ziane.github.io/assets/113150368/fa877775-ca73-4274-8cea-b500591af383)
![Captura de tela 2023-09-17 095619](https://github.com/el1ziane/el1ziane.github.io/assets/113150368/98221c90-4bea-4f74-bedf-3c449d2e274d)
![Captura de tela 2023-09-17 095849](https://github.com/el1ziane/el1ziane.github.io/assets/113150368/f613c9d0-5606-4724-bd4a-0df427fcdb06)
![Captura de tela 2023-09-17 100014](https://github.com/el1ziane/el1ziane.github.io/assets/113150368/5a924df9-8645-41c9-af0c-b9715a8dfeb2)
