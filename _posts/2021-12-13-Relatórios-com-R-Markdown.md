---
layout: post
title: "Relatórios com RMarkdown"
author: "Elias & Ornella"
date: 2021-12-13 14:46:10 +03:00
description: "This is meta description"
featured: true
image: '/assets/images/posts/Relatórios-com-R-Markdown/cape.jpg'
categories: 
  - "Análise de dados"
  - "Relatório"
  - "R"
tags:
  - "Análise de dados"
  - "Relatório"
  - "R"
---

Quando se trabalha com dados, principalmente de forma colaborativa, é muito comum que as análises e seus resultados sejam postos em um relatório a fim de documentar a rotina de trabalho, compartilhar o código desenvolvido e comunicar os resultados obtidos. No R, em particular, isso facilmente pode ser feito por meio de um RMarkdown, um relatório dinâmico poderoso em contar histórias a respeito de dados. Ao proporcionar reprodutibilidade, flexibilidade de formatos e sintaxe bastante simples, propagou-se entre os usuários de R (com larga vantagem, obviamente) e também entre aqueles que não o são - para ser ter uma ideia, é possível usar as linguagens Python, JavaScript e SQL em RMarkdown.

Intuitivamente, o "R" de RMarkdown vem da linguagem de programação R e o "Markdown" está relacionado com a linguagem de marcação do tipo _markdown_, que por sua vez informa apenas sobre a estrutura (conjunto de marcações) do projeto. Logo, RMarkdown nada mais é do que códigos R (no caso em que a programação é feita com R) incorporados em um arquivo _markdown_. 

Adiante, vamos ver como o RMarkdown funciona em sua forma mais simples, porém sem deixar de dizer como ele deve ser minimamente estruturado.

Partindo do ponto que o R + RStudio já está instalado - caso não, deixamos como sugestão a leitura do post [Iniciando na linguagem R](https://observatorioobstetrico.github.io/r/programação/2019/04/14/Iniciando-no-R/) -, um arquivo RMarkdown (.Rmd) precisa ser criado. Para isso, vá em **File > New File > R Markdown...**. A janela **New R Markdown** será aberta. Nela, já podemos definir qual será o título (em **Title**), o nome do autor (em **Author**) e o formato do arquivo (em **Default Output Format**). Em nosso exemplo, vamos criar um arquivo .Rmd em que o título é _Raça das gestantes e puérperas diagnosticadas com SRAG em 2021_ (já que vamos analisar a raça desse grupo em específico que foi diagnosticado com alguma síndrome respiratória aguda grave em 2021), os autores são estes que vos falam e HTML é o tipo do arquivo que queremos que seja gerado. É importante dizer que o RMarkdown exporta  diferentes formatos para além desses exibidos como _default_.

![imagem](/assets/images/posts/Relatórios-com-R-Markdown/fig1.png)

Ao clicar em **OK**, um arquivo .Rmd será aberto no editor de _script_ do RStudio com um roteiro pré-programado. Para não haver confusão, apague tudo o que estiver abaixo do cabeçalho (mais precisamente, tudo o que estiver abaixo do segundo `---`) e salve o arquivo com o nome que julgar adequado. Ah, caso queira alterar o nome do título e/ou o nome dos autores que foram definidos anteriormente, não tem problema, pode modificá-los normalmente. Inclusive, pode excluir a data e o autor se achar que são informações desnecessárias. O que não pode é deixar o arquivo sem o título e o _output_, informações indispensáveis para que o RMarkdown funcione. Em nosso caso, vamos apenas remover a data.

![imagem](/assets/images/posts/Relatórios-com-R-Markdown/fig2.png)

Como já deu para notar, é no cabeçalho (também conhecido como YAML) que estão as configurações gerais do documento. A princípio, determinamos somente o título, o nome dos autores e o formato do arquivo de interesse. Mas podem ser definidas muitas outras informações, como índice, seções, tema etc. Na [documentação do RMarkdown para HTML](https://bookdown.org/yihui/rmarkdown/html-document.html) é possível ver com detalhes todas essas possibilidades.

Após estabelecido o cabeçalho, é a partir daqui que as marcações de texto do _markdown_ conjuntamente aos _chunks_ começam a ser bastante utilizados. As marcações são sintaxes que vão indicar o que são desde títulos de seções, tópicos e imagens a links, códigos e expressões matemáticas, por exemplo:

&nbsp;&bull;&nbsp; o tamanho do título de uma seção é determinado pela quantidade de #, em que quanto menor a quantidade, maior o tamanho da fonte (varia de 1 a 5 _hashtags_);

&nbsp;&bull;&nbsp; uma palavra em negrito deve estar entre `**` e em itálico, entre `_`;

&nbsp;&bull;&nbsp; expressões matemáticas LaTeX podem ser feitas usando a mesma sintaxe LaTeX, desde que estejam entre `$`;

&nbsp;&bull;&nbsp; para incluir uma imagem no meio do texto siga o modelo de marcação: `![título opcional](img/image.png)`; 

&nbsp;&bull;&nbsp; para incluir uma palavra/frase redirecionável: `[palavra/texto](link)`.

Quanto aos _chunks_, eles são blocos de códigos que podem ser adicionados por meio do botãozinho verde contendo a letra C e um sinal de + (à esquerda do botão **Run**, na janela de _script_) ou pelo atalho `Ctrl + Alt + I` no Linux ou Windows ou `Command + Option + I` no Mac. Quando renderizados, eles são adicionados ao arquivo _markdown_ (.md) via pacote `{knitr}`, que executa os códigos dos _chunks_ e gera-os em .md. Em seguida, o pacote `{pandoc}` converte o arquivo .md para a linguagem de programação (neste caso, o R) e no formato de arquivo (neste caso, HTML) escolhidos. Não se preocupe se os dois pacotes mencionados não estiverem instalados, o R fará questão de avisá-lo sobre esse contratempo. Além disso, nos _chunks_ existem uma série de alternativas que permitem ao usuário controlar a execução e os resultados dos códigos, tais como:

&nbsp;&bull;&nbsp; `echo = FALSE`: não exibir o código (TRUE, caso contrário);

&nbsp;&bull;&nbsp; `eval = FALSE`: não executar o código (TRUE, caso contrário);

&nbsp;&bull;&nbsp; `message = FALSE`: esconder mensagens geradas pelo código (TRUE, caso contrário);

&nbsp;&bull;&nbsp; `fig.height = 10`: estipular a altura de uma figura (valor em polegadas);

&nbsp;&bull;&nbsp; `fig.width = 10`: estipular a largura de uma figura (valor em polegadas); 

&nbsp;&bull;&nbsp; `fig.align = 'center'`: centralizar uma imagem.

É sugerido ler a seção [2.5 Markdown syntax](https://bookdown.org/yihui/rmarkdown/markdown-syntax.html) se a intenção é conhecer o conjunto de sintaxes disponível para RMarkdown e a seção [2.6 R code chunks and inline R code](https://bookdown.org/yihui/rmarkdown/r-code.html) para ver a gama de opções que está a serviço dos _chunks_.

Vamos ver como isso funciona na prática ao dar continuidade àquele arquivo .Rmd que criamos alguns parágrafos atrás.

![imagem](/assets/images/posts/Relatórios-com-R-Markdown/fig3.png)

Em nosso "mini relatório", vejam que redigimos um pequeno texto como introdução igualmente como fazemos em editores de texto como o Word e Google Docs, por exemplo. Já para dar início à seção "Os dados", utilizamos o marcador `###`. No entanto, a atenção mesmo fica por conta do _chunk_, para o qual demos o nome de "dados" - nomear um _chunk_ é muito importante para identificar erros, a propósito. Neste caso, informamos que o código fosse avaliado e mostrado no relatório e que mensagens e alertas fossem omitidos.

Agora reparem na próxima seção e nos _chunks_ correspondentes.

![imagem](/assets/images/posts/Relatórios-com-R-Markdown/fig4.png)

Aqui, dividimos a seção "Análise" em duas abas, em que numa tem uma tabela cruzada entre raça e classificação e na outra, um gráfico de barras. A forma de fazer isso é muito simples, com o código HTML `{.tabset}`, mas o resultado é fantástico! Bom, mas voltando às configurações dos _chunks_, observem que dessa vez preferimos não apresentar os códigos, além de que o gráfico fosse centralizado.

Terminado o relatório, o que precisamos fazer agora é renderizar nosso arquivo .Rmd para que ele seja convertido em um arquivo HTML, que foi o formato de _output_ que escolhemos lá no início. Fazemos isso ao utilizar o atalho `Ctrl + Shift + K` no Linux ou Windows ou `Command + Shift + K` no Mac ou simplesmente clicando no botão **Knit** (que está acompanhado por um novelo de lã azul). Na realidade, é recomendável que a cada _chunk_ construído seja feita a renderização do documento, principalmente se o seu relatório for muito extenso e com muitos _chunks_. Dessa forma, é possível acompanhar se o resultado está ficando ao seu agrado como também fica mais fácil identificar possíveis erros.

Após "dar knit" em nosso RMarkdown, o relatório em HTML gerado é o que está na figura abaixo.

![imagem](/assets/images/posts/Relatórios-com-R-Markdown/fig5.png)

Legal, né?

Ainda que de forma simples, mostramos como o RMarkdown pode conectar o documentar, o compartilhar e o comunicar dos dados de maneira prática e sem dar maiores dores de cabeça ao usuário (pois olhem só, propusemos um relatório em HTML sem precisar ter qualquer noção de HTML!). Além do mais, sua flexibilidade em se adequar aos diferentes tipos de linguagem de programação e formato de arquivo consegue agradar aos mais diversos perfis de profissionais, mesmo aqueles com pouca experiência em programação. 

A última e grande notícia é que o RMarkdown não se limita a um relatório estático com códigos e respectivos resultados. Com ele, também é possível fazer trabalhos acadêmicos, artigos, currículos profissionais, correio personalizado (encaminhar documentos em PDF automaticamente), slides, livros (o livro [R Markdown: The Definitive Guide](https://bookdown.org/yihui/rmarkdown/), recomendado mais de uma vez neste post, é todo feito em? RMarkdown!), painéis interativos (geralmente por meio do pacote `{flexdashboard}`)... No bom sentido da expressão, o que foi mostrado aqui foi só a pontinha do _iceberg_!