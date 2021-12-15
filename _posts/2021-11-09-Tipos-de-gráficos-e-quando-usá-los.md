---
layout: post
title: "Tipos de gráficos e quando usá-los"
date: 2021-12-15 14:46:10 +03:00
description: "This is meta description"
featured: true
image: '/assets/images/posts/Tipos-de-gráficos/cape.jpg'
categories: 
  - "Gráficos"
  - "Análise de dados"
tags:
  - "Gráficos"
  - "Análise de dados"
---

Muitos de nós recebemos, nas últimas 72 horas, mais inputs que produzem mudanças, criam projetos e alteram prioridades do que nossos pais recebiam em um mês inteiro, talvez até em um ano.
Com a transformação do mundo analógico para digital, os dados são gerados em praticamente todas as ações realizadas pelo ser humano, cliques em anúncios, curtidas em mídias sociais, compartilhamentos, transações, conteúdo de streaming e muito mais. “Dados são o petróleo do século 21” e a transformação desse universo de dados em informações é o que tem diferenciado as empresas em todos os segmentos de mercado. É ai que entra uma ferramenta muito importante para ajudar a transmitir essas informações: os gráficos. 
Gráficos são representações visuais utilizadas para exibir dados, e quando utilizados da maneira correta, nos permitem uma interpretação rápida e fácil de todas aquelas informações que estão agrupadas, por isso, é interessante conhecer os principais gráficos.

Quando entramos no ramo de visualização de dados, muita coisa entra em discussão. Entender o contexto é extremamente importante, entender o público, contextualizar uma história, conhecer os seus dados, as cores dos gráficos podem ser sua amiga tanto quanto sua inimiga. Enfim, é muita coisa. O foco deste post é falar um pouco sobre os principais gráficos utilizados no dia a dia e falar, de uma forma mais técnica, quando é recomendado utilizá-los. Caso queira se aprofundar mais no ramo da visualização recomendamos fortemente o livro **Storytelling com dados - um guia sobre visualização de dados para profissionais de negócios** da autora Cole Nussbaumer Knaflic, inclusive, algumas discussões presentes neste post foram retiradas deste livro. Vale ressaltar também, que todos os gráficos exibidos abaixo foram feitos no Software R e a maioria utilizando o pacote `ggplot`. Não é o foco do post ensinar a construir os gráficos, caso tenha interesse você pode acessar o material produzido pelo **ensinaR** onde eles explicam com clareza tudo o que precisa saber para construir lindos gráficos com o `ggplot` e outros pacotes, baste clicar [aqui](https://daslab-ufes.github.io/ggplot2_intro/) e [aqui](https://daslab-ufes.github.io/ggplot2_misc/) também.

## Gráficos de barras

Tenho certeza que você já viu um gráfico de barras pelo menos uma vez na vida. Gráficos de barras são extremamente comuns e muito utilizados. Esse tipo de gráfico é utilizado para passar informações de dados categóricos onde, cada barra no gráfico representa uma categoria (eixo x) e a altura de cada barra representa uma agregação específica  como a soma dos valores (eixo y) por exemplo. Ao olhar para ele, rapidamente identificamos qual categoria é maior e qual a diferença de tamanho entre as categorias. Pela sua simplicidade algumas pessoas tendem a evitar esse tipo gráfico, mas é exatamente por esse motivo que devemos utilizá-los mais. Existem algumas variações desses gráficos como os de barras verticais (ou de colunas), de barras verticais empilhadas, de barras horizontais, etc. Vamos ver alguns exemplos.  

No exemplo abaixo vamos imaginar um cenário simples, onde temos um banco de dados que contém algumas informações sobre os tipos de carros. Caso seja necessário mostrar para o público simplesmente a quantidade de veículos em cada tipo, o gráfico de barras irá nos atender muito bem. Veja como é fácil olhar e entender a informação que está sendo transmitida.

![imagem](/assets/images/posts/Tipos-de-gráficos/fig1.png)

Caso você queira passar informações que contenham mais de uma categoria, o gráfico de barras também é interessante. veja:

![imagem](/assets/images/posts/Tipos-de-gráficos/fig2.png)

Note que também é fácil identificar séries faltantes em uma determinada categoria, por exemplo, no tipo "Small" podemos notar facilmente a ausência da opção "Driver & Passenger". Podemos puxar um gancho para falar sobre a largura das barras. Bom, não existe uma regra, basta se atentar para que as barras não fiquem finas demais ou grossas demais, um meio termo pode ser interessante.

## Gráfico de dispersão 

Um gráfico de dispersão pode ser utilizado quando se deseja mostrar a associação entre variáveis de uma forma rápida e assertiva. Podemos observar simultaneamente os dados representados por um marcador cuja posição depende dos seus valores nas colunas determinados nos eixos X e Y. Assim, conseguimos ver então o que acontece com uma variável quando a outra se altera, ajudando desta forma a verificar a relação entre elas. Para ilustrar isso, pense que temos um banco de dados contendo informações sobre veículos. Temos uma variável que representa quantas milhas um veículo percorre com um litro de gasolina e uma variável que representa o peso deste veículo. Será que existe alguma relação entre essas variáveis? Bom, um gráfico de correlação é perfeito para verificar essa hipótese. 

![imagem](/assets/images/posts/Tipos-de-gráficos/fig3.png)

Com um simples gráfico de dispersão já podemos mostrar muitas informações, porém, esse é um gráfico um pouco mais "avançado". Com isso, a depender do seu público, você irá precisar incrementar ele um pouco mais para facilitar o entendimento ou até mesmo explicar o objetivo do gráfico. Você pode também destacar algumas informações neste tipo de gráfico, como uma linha separando os valores pela média por exemplo.

## Histogramas 

O gráfico de histograma é um dos mais utilizados quando se trata de mostrar a distribuição dos dados. Se você deseja apresentar ou tirar conclusões de um grande conjunto de dados e está trabalhando com conceitos envolvendo frequências, sejam absolutas ou relativas, o histograma é uma excelente escolha.
Ele nos permite observar facilmente informações sobre centralidade, amplitude e simetria. Um histograma pode ser confundido com um gráfico de barras pois é formado justamente por barras, entretanto, este tipo de gráfico é usado para dados contínuos, diferente dos gráficos de barras. Os espaços entre gráficos de barras são recomendados também para diferenciar esses gráficos. Em um histograma, a base de cada uma das barras representa uma classe e a altura representa a quantidade ou frequência absoluta com que o valor de cada classe ocorre. O objetivo principal do histograma é ilustrar como uma determinada amostra de dados ou população está distribuída. Para exemplificar melhor, vamos plotar 2 histogramas.

![imagem](/assets/images/posts/Tipos-de-gráficos/fig4.png)

![imagem](/assets/images/posts/Tipos-de-gráficos/fig5.png)

Note como o formato dos gráficos são diferentes. Existem vários tipos de histogramas, simétricos, distorcidos à direita ou à esquerda, multimodal, etc. Essa diferença tem relação com os dados e sua distribuição e é exatamente isso que o histograma nos permite ver com facilidade. 

## Boxplot

Assim como o histograma, o boxplot também nos fornece informações sobre variabilidade, locação dos dados, etc. Porém, o gráfico é bem diferente. Ele possui um formato de caixa usando como referência os valores mínimos e máximos, primeiro quartil, mediana, terceiro quartil e outliers. A parte central do gráfico (a caixa) representa valores do primeiro quartil (Q1)  ao terceiro quartil (Q3) possuindo uma linha no meio que representa a mediana ou segundo quartil (Q2). As hastes inferiores representam do primeiro quartil até o menor valor, assim haste superior representa do terceiro até o maior valor. Valores outlier normalmente são representados por pontos, ficando acima da haste ou superior e/ou abaixo da haste inferior, assim, todo o boxplot representa 100% dos seus dados. Veja um exemplo abaixo:

![imagem](/assets/images/posts/Tipos-de-gráficos/fig6.png)

Para o exemplo acima utilizamos o banco de dados `iris`, presente no pacote base do R. O gráfico nos mostra a distribuição dos dados de três espécies. Rapidamente percebemos que os dados possuem alocações diferentes. O boxplot da "setosa" é mais achatado, indicando uma variabilidade menor dos dados, além disso está localizado na parte inferior dos dados, indicando uma mediana e média menor. Olhando agora para a espécia "virginica" vemos que é a única que possui um outlier, ela também possui a maior mediana entre as três. O boxplot é um excelente gráfico para nos dar uma clareza sobre como seus dados quantitativos estão distribuídos e fazer comparações entre classes. Também pode ser usado em conjunto com o histograma como complementação. Apesar de ser uma boa opção de gráfico, alguns cuidados devem ser tomados. o grupo **from Data to Viz** fez uma postagem muito legal comentando alguns cuidados e algumas maneiras diferentes de produzir um boxplot, [veja](https://www.data-to-viz.com/caveat/boxplot.html).

## Gráfico de linhas 

Se você quiser exibir tendências ao longo do tempo, um gráfico de linhas será ideal, principalmente quando se deseja representar dados referentes a séries temporais. Os gráficos de linhas são formados por uma série de pontos que se conectam por meio de uma linha. O eixo x, na maioria das vezes, será formado por dados contínuos que representam tempo, seja em anos, meses, dias, horas ou outro nível de medida de tempo, enquanto o eixo y representa o outro dado em questão. Este tipo de gráfico cai muito bem quando se tem mais de uma classe em seus dados, ou seja, quando se deseja comparar os resultados. Veja no exemplo abaixo como fica bem intuitivo entender as informações:

![imagem](/assets/images/posts/Tipos-de-gráficos/fig7.png)

![imagem](/assets/images/posts/Tipos-de-gráficos/fig8.png)

Vale ressaltar que gráficos de linhas são ótimos para representar variáveis de tempo, mas também pode representar strings. [Aqui](https://doc.arcgis.com/pt-br/insights/latest/create/line-graph.htm) você pode ver um ótimo exemplo disso.
Caso tenha curiosidade, você pode acessar informações sobre a base de dados do gráfico acima [aqui](https://ggplot2.tidyverse.org/reference/economics.html).

## Gráficos não recomendados 

Como já dito, gráficos devem ser utilizados para facilitar o nosso entendimento sobre os dados, nos auxiliar na hora de transmitir informações. Porém, alguns tipos de gráficos devem ser evitados pois podem nos atrapalhar. Gráficos de pizza, de rosca e gráficos 3D não são uma boa idéia.

### Gráficos de pizza/3D

Olhe para o gráfico abaixo atentamente e tente adivinhar qual é a maior parte, além disso, responda quanto tempo demorou para analisar este gráfico e extrair as informações que eram para ser simples.

![imagem](/assets/images/posts/Tipos-de-gráficos/fig9.png)

Agora olhe para o gráfico abaixo e tire suas próprias conclusões sobre este tipo de gráfico.

![imagem](/assets/images/posts/Tipos-de-gráficos/fig10.png)

Talvez no exemplo acima você tenha conseguido adivinhar as proporções com facilidade, mas veja alguns motivos que podem causar problemas ao utilizar este tipo de gráfico. Ao aplicar a perspectiva 3D em um gráfico, separando e inclinando as fatias, pode gerar uma distorção indesejada, fazendo com que as fatias maiores pareçam menores ou vice-versa. O problema do 3D se estende para outros tipos de gráficos, adicionar 3D à um gráfico introduz elementos desnecessários que não ajudam em nada na visualização, muito pelo contrário, apenas atrapalham. O único motivo plausível para usar 3D é se você de fato precisa representar uma terceira dimensão, fora isso, **nunca use 3D**.

Falando agora exclusivamente dos gráficos de pizza (sem o 3D) ele continua sendo uma péssima opção de gráfico. Estudos comprovam que o olho humano não consegue atribuir corretamente valores quantitativos no espaço bidimensional, principalmente se as partes tiverem tamanhos parecidos. Quando os tamanhos das fatias não são parecidos você até consegue determinar facilmente qual é maior, mas dificilmente saberá dizer o quanto. De forma mais clara, é bem difícil ler um gráfico de pizza, o que vai contra um dos principais objetivos de utilizar gráficos.

Vamos mostrar o quão mais fácil é interpretar um resultado quando usamos um simples gráfico de barras, porém, barras horizontais. A única diferença do gráfico abaixo para o mostrado no início do post é que as barras estão dispostas no eixo horizontal. 
Gráficos de barras horizontais são recomendados quando os nomes das suas categorias são longos. Além disso normalmente processamos as informações da esquerda para a direita, fazendo "Zs" com os olhos na tela da página, com a estrutura do gráfico horizontal conseguimos primeiro ler a categoria antes dos dados, portanto, chegamos aos dados já sabendo o que eles estão representando.

![imagem](/assets/images/posts/Tipos-de-gráficos/fig11.png)

### Gráfico de rosca

Podemos fazer o mesmo esquema que fizemos com o gráfico de pizza. Olhe para o gráfico abaixo e tente adivinhar as proporções. Consegue dizer facilmente a diferença de tamanho entre eles?

![imagem](/assets/images/posts/Tipos-de-gráficos/fig12.png)

Agora olhe para os valores:

![imagem](/assets/images/posts/Tipos-de-gráficos/fig13.png)

O problema dos gráficos de rosca é um pouco parecido com os de pizza. A diferença é que aqui você não está comparando ângulos e áreas, mas sim o comprimento de um arco com outro. 

Bom, agora que já conhece os principais gráficos e possui uma boa ideia de quando pode utilizá-los, a nossa dica é que procure outros temas que possam agregar neste ramo como, por exemplo, aprofundar na interpretação dos gráficos, criar gráficos no R, entender melhor o público e saber quando e qual gráfico se encaixa melhor, enfim. Reforçamos então a leitura do livro **Storytelling com dados - um guia sobre visualização de dados para profissionais de negócios**.

## Referências 

<https://www.r-graph-gallery.com/index.html>

<https://www.alura.com.br/artigos/melhorando-a-analise-com-o-boxplot?gclid=CjwKCAiAtdGNBhAmEiwAWxGcUjXZW3hKIGbivD45SO0tQEtv9j1G0cBqr5D4dZLZr5rjgqukW7dcfxoCXUkQAvD_BwE>

<https://daslab-ufes.github.io/ggplot2_misc/>

<https://daslab-ufes.github.io/ggplot2_intro/>

<https://gestaodesegurancaprivada.com.br/grafico-o-que-e-objetivo-caracteristica-e-tipos/#Graficos-escolha-ideal>

<https://www.numerapeopleanalytics.com/insights/grfico-de-correlao>

<https://www.fm2s.com.br/grafico-de-dispersao/>
