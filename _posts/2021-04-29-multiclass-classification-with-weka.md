---
layout: post
title:  "Classificação Multiclasse com Weka"
categories: [classificação, multiclasse, weka, tutorial]
image: assets/images/2.jpg
---
Nessa postagem, vamos realizar nosso primeiro projeto de classificação multiclasse utilizando o Weka. Caso ainda não tenha feito, talvez você queira ler antes o artigo onde eu falo [como instalar e iniciar o Weka pela primeira vez](./_posts/2021-04-08-install-weka.html). Pode ir lá primeiro. Estarei esperando por aqui. Mas caso você já tenha lido o artigo supracitado, basta seguir adiante.

O passo-a-passo aqui apresentado poderá ser usado como base para todos os demais projetos que você queira realizar com a ferramenta. Em geral, faremos praticamente sempre o seguinte:

  1. carregar os dados,  
  2. analisar os dados,  
  3. empregar os algoritmos mais adequados conforme os dados disponíveis,  
  4. avaliar os resultados de cada algoritmo empregado,  
  5. apresentar os resultados finais.

Vamos, então, à diversão e com o Weka já aberto clique em  **Explorer**.

image



### Carregando os dados
Nesse primeiro projeto, vamos utilizar uma das bases de dados que já vem com a instalação padrão da ferramenta. Na janela do Explorer que se abriu, clique agora em **Open file** e vá até a pasta **data/** que, por sua vez, se encontra dentro da pasta onde você instalou o Weka. No meu caso, no Linux, as bases de dados se encontram no seguinte caminho: **~/ml/weka-3-8-6/data/**.

Nesse local você encontrará vários arquivos com a extensão *.arff*. Clique em **iris.arff** e depois em **Abrir** (ou *Open*). Pronto, os dados foram carregados com suscesso e você verá a tela semelhante à figura que se segue:

image

### Analisando os dados
Com os dados carregados no Explorer, a melhor coisa a se fazer primeiramente é dar uma olhada em geral no que temos à disposição antes de se começar a modelar diretamente. Deve-se analisar como se apresenta a distribuição dos dados para cada atributo e a relação intrínseca entre os próprios atributos. Dessa forma, vislumbramos a melhor maneira de preparar/corrigir os dados e também podemos decidir melhor (e com a prática isso vai se tornando cada vez mais instantâneo) quais os modelos e técnicas específicas utilizar para esse caso específico.

#### Estatísticas