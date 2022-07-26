---
layout: post
title:  "Classificação Multiclasse com Weka"
categories: [classificação, multiclasse, weka, tutorial]
image: assets/images/2.jpg
---
Vamos iniciar nosso primeiro projeto utilizando o Weka.

O passo-a-passo aqui apresentado poderá ser usado como base para todos os demais projetos que você queira realizar com a ferramenta. Em geral, faremos praticamente sempre o seguinte:

  1 - carregar os dados,  
  2 - analisar os dados,  
  3 - empregar os algoritmos mais adequados conforme os dados disponíveis,  
  4 - avaliar os resultados de cada algoritmo empregado,  
  5 - apresentar os resultados finais.

Vamos, então, à diversão!

image

Com o Weka aberto clique em  **Explorer**.

### Carregando os dados
Nesse primeiro projeto, vamos utilizar uma das bases de dados que já vem com a instalação padrão da ferramenta. Na nova janela do Explorer que se abriu, clique agora em **Open file** e vá até a pasta **data/** que, por sua vez, se encontra dentro da pasta onde você instalou o Weka. No meu caso, no Linux, as bases de dados se encontram no seguinte caminho: **~/ml/weka-3-8-6/data/**.

Nesse local você encontrará vários arquivos com a extensão *.arff*. Clique em **iris.arff** e depois em **Abrir** (ou *Open*). Pronto, os dados foram carregados com suscesso e você verá a tela semelhante à figura que se segue:

image

