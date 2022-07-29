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
Clique em **New** para iniciar um novo experimento. Em **Experiment Type** mude o **Number of folds** para 5. Como falamos anteriormente, como não há muitas instâncias na base de dados, o ideal é que tenhamos menos grupos com mais instâncias. Em nosso caso concreto, 5 grupos de 30 instâncias.

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



### Analisando os dados
Com os dados carregados no Explorer, a melhor coisa a se fazer primeiramente é dar uma olhada em geral no que temos à disposição antes de se começar a modelar algo de súbito. Deve-se analisar como se apresenta a distribuição dos dados para cada atributo e a relação intrínseca entre os próprios atributos. Dessa forma, vislumbramos a melhor maneira de preparar/corrigir os dados e também podemos decidir melhor (e com a prática isso vai se tornando cada vez mais instantâneo) quais os modelos e técnicas específicas a se utilizar para cada caso específico.

#### Estatísticas
No painel **Current relation** nós já podemos ver diversas informações sobre nossa base de dados. Ficamos sabendo que há, por exemplo, 150 instâncias e para cada instância, 5 atributos, sendo 4 atributos de entrada (*inputs*) e um de saída (*output*). Como só há apenas 150 instâncias, para melhores resultados, seria melhor dividir as instâncias em 5 grupos de 30 (ao invés de 10 grupos de 15) para uma eventual validação cruzada (*cross-validation*) na hora de avaliar os algoritmos no futuro.

Como há também um pequeno número de atributos, podemos investigá-los um a um, mais a fundo. Para isso, clique sobre cada um dos atributos (à esquerda) e veja suas informações mais detalhadas (à direita). Veremos, com efeito, que não há valores ausentes em nenhum dos atributos. Além disso, todos os valores de entrada (*inputs*) são *numéricos* e todos estão no mesmo intervalo entre 0 e 8. O último atributo é a saída (*output*) que por sua vez é *nominal* e possui três valores distintos. Ademais, as classes estão perfeitamente balanceadas, o que significa dizer que cada uma possui exatamente a mesma quantidade de instâncias. Nesse caso, 50 instâncias em cada classe. Conforme essas características, podemos pensar tanto em normalizar como em padronizar os dados ao manipulá-los antes de criar nosso modelo.

#### Distribuição
Clique agora em **Visualize all** e vamos dar uma olhada na distribuição gráfica de cada atributo.

image

Também a representação gráfica dos dados nos traz valiosadas informações. Nós podemos ver alguma interseção entre os dados, mas, no geral, as distribuições são bem definidas e separadas o que provavelmente vai nos facilitar a separar as três diferentes classes. O atributo *sepalwidth* (largura da [sépala](https://pt.wikipedia.org/wiki/S%C3%A9pala)) possui praticamente uma distribuição normal (gausiana). As demais três entradas (*inputs*) também apresentam distribuições semelhantes à normal (se tivéssemos mais instâncias, provavelmente isso se tornaria mais evidente) e com concentração de valores nas extremidades de cada distribuição. Os gráficos também espelham o fato das classes estarem perfeitamente balanceadas.

#### Interação entre os Atributos
Clique agora na aba **Visualize** e vamos rever algumas interações entre os atributos. Maximize a janela que se abriu para que todos os gráficos possam ser visualizados concomitantemente. Aumente o **PointSize** para 3 para ficar mais fácil de se ver os pontos nos gráficos e clique em **Update**.

Vemos que há uma boa separação das classes nos gráficos de dispersão (*scatter plots*), como em *petalwidth* por *sepallenght* e *petalwidth* por *sepalwidth*. Dessa forma podemos pensar em aplicar métodos lineares e talvez árvores de decisão (*decision trees*) ou métodos de aprendizado baseado em instâncias (*instance basead learning*) em nossa abordagem. Provavelmente não precisaremos gastar muito tempo ajustando os algoritmos nem utilizando técnicas mais elaboradas para a modelagem.

No próximo artigo iremos dar prosseguimento a esse nosso primeiro experimento na prática com Weka. Te vejo na próxima postagem.

73