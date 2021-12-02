---
layout: post
title: "Iniciando na linguagem R"
date: 2019-04-14 14:46:10 +03:00
description: "This is meta description"
featured: true
image: '/assets/images/posts/iniciando-no-R/cape.jpg'
categories: 
  - "R"
  - "Programação"
tags:
  - "R"
  - "Programação"
---

Nos dias atuais o uso de linguagens de programação têm sido indispensáveis no dia a dia de profissionais das mais diversas áreas, dentre elas ouvimos frequêntemente falar de Java, Python, Ruby e várias outras. Essas ferramentas nos possibilitam otimizar processos do dia a dia, como também auxiliar na resolução de problemas mais complexos.

## O que é R ?
O R é uma linguagem de programação e também um ambiente de análise de dados criada por Robert Gentleman e Ross Ihaka. Tem sido amplamente utilizada no mundo acadêmico devido a sua alta eficácia para lidar com todos os tipos de dados e lidar com problemas complexos, e tem ganhado cada vez mais espaço nos últimos anos nas mais variadas áreas e mercados. Tudo isso não é atoa, o R tem sido visto não mais apenas como uma linguagem de programação, mas como um conjunto de soluções estatísticas e computacionais extremamente poderoso que permite a realização de investigações profundas em bases de dados.

## Por que R ?
Um dos principais benefícios de se utilizar o R se da pelo fato de ele ser um sofware open source (código aberto) e gratuito, em que está constantemente evoluindo devido as contribuições da própria comunidade, à qual é extremamente engajada no desenvolvimento de bibliotecas como também no suporte aos usuários.

No R podemos programar, o que nos permite otimizar processos envolvendo análise de dados. Podemos vizualizar os dados de forma gráfica, facilitando a obtenção de 'insights' de forma rápida. Tudo isso em conjunto com a eficácia que conseguimos criar relatórios através de ferramentas como o RMardown, o R nos permite realizar trabalhos com uma ótima reprodutibilidade, fator extremamente importante na realização de pesquisas.

## Como começar no R ?

Para iniciarmos no R devemos escolher um ambiente de desenvolvimento integrado (IDE) para podermos trabalhar. A maioria dos usuários utilizam o RStudio, o qual é extremamente intuitivo de se utilizar, e dispõe de um ótimo ambiente de trabalho.

Realizada a escolha do ambiente de desenvolvimento que será utilizado, devemos instalar o R em nossa maquina, para isto, podemos seguir os seguintes passos: 

**Instalação do R base**

O R base pode ser baixado diretamente da rede de distribuição do R em [CRAN](https://cran.r-project.org/), onde primeiramente deve-se escolher o sistema operacional (Linux, macOS ou Windows).

![imagem](/assets/images/posts/iniciando-no-R/cran.jpg)

Caso o sistema operacional escolhido for o Windows, deve-se escolher o subdiretório *base*. 

![imagem](/assets/images/posts/iniciando-no-R/cran2.jpg) 

Posteriormente basta fazer o download.
![imagem](/assets/images/posts/iniciando-no-R/cran3.jpg)

Feito isso, basta abrir o arquivo executável que foi baixado na máquina e seguir os passos requeridos na instalação. Para usuários de Linux e macOS, após escolher o link de download do sistema operacional, com uma breve leitura das instruções que são disponibilizadas em texto é possível prosseguir com a instalação sem muitas dificuldades.

**Instalação do RStudio**

Pode ser baixado diretamente do site oficial em [RStudio](https://www.rstudio.com/).

![imagem](/assets/images/posts/iniciando-no-R/rstudionew.jpg)

Atualmente são disponibilizadas quatro versões do RStudio, sendo duas com licença comercial e duas com licença Open Source. Nosso interesse está no RStudio Desktop, o qual é gratuito e possui uma licença Open Source.

![imagem](/assets/images/posts/iniciando-no-R/rstudio2.jpg)

Depois disso, basta realizar o download e seguir as instruções de instalação do arquivo executável.

Após instalar o R e o RStudio, será com o RStudio que iremos interagir, assim que abrirmos ele teremos a seguinte tela:

![imagem](/assets/images/posts/iniciando-no-R/rsutdio3.jpg)

Essas são as quatro principais áreas do ambiente do RStudio, cada uma é descrita a seguir:

&nbsp;1. Onde se escreve os códigos (principalmente arquivos do formato .R).

&nbsp;2. Área do console, onde se executa os códigos.

&nbsp;3. Nessa área temos diversas utilidades frequentemente utilizadas:

&nbsp;- Podemos acessar arquivos e pastas do computador pela aba *Files*. 

&nbsp;- Na aba *Plots* visualizamos o resultado gráfico caso um comando desse tipo tenha sido executado. 

&nbsp;- Em *Packages* podemos manusear pacotes (instalar, atualizar ou deletar). 

&nbsp;- Na aba *Help* temos acesso à documentação de uma determinada função quando utilizado o comando help() ou ?.

&nbsp;4. Em *Environment* temos acesso a todos os objetos criados, e na aba *History* é disponível o histórico de códigos executados. 

Por padrão, o R lê as linhas de códigos da esquerda para a direita indo de cima para baixo, porém, ao se deparar com operações matemáticas ele respeita algumas prioridades onde, da operação com maior prioridade para a menor temos: potenciação > multiplicação ou divisão > adição ou subtração. Caso houver a necessidade de alterar essa ordem, isso pode ser feito utilizando parênteses.

Para uma primeira interação com o ambiente de desenvolvimento, podemos utilizá-lo como uma calculadora ao dar entrada no console comandos como os listados abaixo:

``` r
# Potencia
2^5

# Multiplicação
2 * 5

# Divisão
2/5

# Adição
2 + 5

# Subtração
2 - 5
```

Para verificar a prioridade das operações vemos os seguintes exemplos:

``` r
# Potência > Multiplicação > Soma
2^2 + 5 * 2
```

     [1] 14

``` r
# Multiplicação > Potência > Soma
2^2 + (5 * 2)
```

     [1] 14

``` r
# Potência > Soma > Multiplicação
(2^2 + 5) * 2
```

     [1] 18

Agora que conseguimos realizar calculos simples com o R, vamos falar de variáveis. As variáveis são onde iremos "guardar" objetos, e são de extrema importância por serem usadas a todo momento. O ato de "guardar" objetos dentro de variáveis é chamado de atribuição, e pode ser feito com <- ou =, veremos alguns exemplos a seguir:

``` r
# Variável x recebe o número 5.
x <- 5

# Variável x recebe o número 5.
x = 5

# Variável x recebe o número 5.
y = (2^2 + 6) - 4
x <- y - 1
```

Dentre as classes de objetos existentes no R, quatro deles se destacam por serem mais usados na prática, abaixo temos alguns exemplos e verificamos a classe de objetos que cada variável atribuída pertence:

``` r
# numeric/números reais.
x <- 0.9
class(x)
```

     [1] "numeric"

``` r
# integer/números inteiros.
x <- 5L
class(x)
```

     [1] "integer"

``` r
# character.
x <- "gestante"
class(x)
```

     [1] "character"

``` r
# logical/valores lógicos (TRUE,FALSE).
x <- TRUE
class(x)
```

     [1] "logical"

Obs: Note que os valores lógicos são apresentados em letra maiúscula, isso é muito importante, pois o R diferencia letras maiúsculas de minúsculas, então valores lógicos só são reconhecidos assim se usados como TRUE ou FALSE.

Vale mostrar também que cada valor lógico assume um valor numérico em específico, sendo TRUE referente ao valor 1, e FALSE referente ao valor 0: 

``` r
TRUE + TRUE + FALSE + 2*TRUE
```

     [1] 4

Pensando agora nos objetos com diferentes estruturas frequentemente utilizados no dia a dia por usuários de R, temos os seguintes:

&nbsp;- Vetor

&nbsp;- Matriz

&nbsp;- Array

&nbsp;- Data Frame

&nbsp;- Lista

Todos estes objetos tem a característica de poder conter diversos valores ao mesmo tempo, e podem ser atribuídos à uma variável como fizemos com valores isolados anteriormente, e então podemos utilizar estruturas com milhares de dados em apenas uma variável para realizar manipulações e análises sem muitos problemas.

## Dicas

Durante a construção de um script (arquivo de códigos, geralmente arquivos .R) é de extrema importância incluir explicações a respeito do que está sendo feito, pois é importante que a leitura do script esteja o mais clara possível para outras pessoas que forem ler entenderem o que foi feito, o que inclui também a própria pessoa que fez o script, já que é muito comum ter que retornar à um script feito semanas ou meses atrás, e caso as linhas de códigos não possuirem orientações, o próprio autor terá dificuldade de entender o que foi feito. A inclusão de explicações pode ser feita através de comentários utilizando o símbolo #, como por exemplo:

``` r
# Variável que contém o valor 2.
x <- 1 + 1
```

O símbolo # pode ser usado para informar quem for ler o código posteriormente, mas também pode ser usado para dizer qual parte do seu script você não quer que seja executado, vejamos:

``` r
# É executado
x <- 1 + 1  

# Não é executado
#y <- 5 - 5
```

Uma breve explicação do que o script faz como um todo também é uma boa prática a se adotar no início de cada arquivo.

``` r
# Script para ensinar as utilidades de se comentar linhas de códigos

# É executado
x <- 1 + 1  

# Não é executado
#y <- 5 - 5
```

Obs: É possível comentar blocos de linhas de códigos de uma só vez, basta selecionar o que você não quer que seja executado e utilizar o comando ctrl + shift + c.

Sempre que houver a dúvida sobre o que um determinado comando ou função faz, podemos pedir ajuda no próprio R através do comando help() ou ?, por exemplo:

![imagem](/assets/images/posts/iniciando-no-R/help.jpg)

Vemos na figura acima que ao dar entrada no comando *help("hist")* no console, a aba *Help* foi atualizada com uma descrição da função *hist*.

Caso o console retorne algum erro após tentar executar um código, uma dica é copiar o erro e pesquisá-lo no google, pois é muito provável que alguém já tenha tido o mesmo erro, o que torna fácil na maioria das vezes de se encontrar soluções.

Todo o conteúdo aqui abordado serve de introdução às pessoas que nunca tiveram contato com o R anteriormente. A comunidade é extremamente ativa, e é possível encontrar um vasto mundo de tutoriais e guias com uma simples pesquisa na internet, facilitando a aprendizagem.