---
layout: post
title:  "Classificação Multiclasse com Weka (02)"
categories: [classificação, multiclasse, weka, tutorial]
image: assets/images/2.jpg
---
Nesse artigo, vamos dar sequência ao nosso primeiro projeto de classificação multiclasse utilizando o Weka. A primeira parte do projeto se encontra em [Classificação Multiclasse com Weka](https://ml.bahien.se/multiclass-classification-with-weka).

Conforme o passo-a-passo apresentado abaixo, já falamos de como carregar e analizar os dados utilizando o Weka. Pelas características da base de dados que temos em mãos, a manipulação/preparação dos dados não foi necessária. Agora vamos avaliar os algoritmos que fazem mais sentido utilizar nos dados que temos disponíveis:

  1. ~~carregar os dados~~,  
  2. ~~analisar os dados~~,  
  3. ~~manipular os dados~~,  
  4. empregar os algoritmos mais adequados conforme os dados disponíveis,  
  5. avaliar os resultados de cada algoritmo empregado,  
  6. apresentar os resultados finais.

Vamos, então, voltar à diversão e iniciar a avaliação de alguns algoritmos. Se você ainda não o fez, feche o **Explorer** caso ele esteja aberto e abra o **Weka Experimenter Environment**.

image



### Escolhendo e avaliando os algoritmos
Clique em **New** para iniciar um novo experimento. Em seguida, em **Experiment Type** mude o **Number of folds** para 5. Como falamos anteriormente, como não há muitas instâncias na base de dados, o ideal é que tenhamos menos grupos com mais instâncias. Nesse caso concreto, 5 grupos de 30 instâncias.

Em **Datasets** clique agora em **Add new...** e selecione novamente a nossa base de dados em **caminho/para/data/iris.arff**. Substituta *caminho/para/* de acordo com a sua própria instalação.

Agora em **Algoritms** clique em **Add new...** e vamos selecionar os seguintes algoritmos:

- rules.ZeroR  
- bayes.NaiveBayes  
- functions.Logistic  
- functions.SMO  
- lazy.IBk  
- rules.PART  
- trees.REPTree  
- tress.J48  

Vamos falar de cada um desses algoritmos com mais detalhes em outros artigos. No momento estamos apenas colocando a mão na massa e aprendendo como usar o Weka. A parte teórica sobre os algoritmos pode ficar momentaneamente de lado.

Selecione agora o algoritmo IBk e clique em **Edit selected**. Vamos editar um parâmetro desse algoritmo antes de iniciar o experimento. Mude, portanto, **KNN** para 3 e clique em **OK**. 

image

Finalmente vamos dar início ao nosso experimento. Clique no painel **Run** e em seguida em **Start**. O experimento não durará mais do que alguns segundos.

image

### Analisando os resultados
Clique agora na aba **Analyse** e, em seguida, clique no botão **Experiment** para carregar os resultados do nosso experimento que acabamos de realizar. Agora clique no botão **Perform test**. Será feita uma análise comparativa do algoritmo ZeroR com todos os demais algoritmos que nós selecionamos anteriormente.

image

Na imagem pode-se ver que todos os algoritmos tiveram um resultado melhor do que o algoritmo ZeroR. A diferença estatística é, de fato, considerável. Os resultados apontam também que tanto a Logistic Regression e a SVM possuem as acurácias mais elevadas. Vamos, portanto, realizar a mesma comparação, mas tomando agora a Logistic Regression como base. Escolhemos a Logistic Regression por ser um modelo muito mais simples. E como se diz por aí, a simplicidade é o mais alto grau de sofisticação.