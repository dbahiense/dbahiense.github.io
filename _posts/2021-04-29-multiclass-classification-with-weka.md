---
layout: post
title:  "Classificação Multiclasse com Weka"
categories: [classificação, multiclasse, weka, tutorial]
image: assets/images/2.jpg
---
Nessa postagem, vamos realizar nosso primeiro projeto de classificação multiclasse utilizando o Weka. Caso ainda não tenha feito, talvez você queira ler antes o artigo onde eu falo [como instalar e iniciar o Weka pela primeira vez](https://ml.bahien.se/install-weka). Pode ir lá primeiro. Estarei esperando por aqui. Caso você já tenha lido o artigo supracitado, basta seguir adiante.

O passo-a-passo aqui apresentado poderá ser usado como base para quase todos os demais projetos que você queira realizar com a ferramenta. Em geral, faremos praticamente sempre o seguinte:

  1. carregar os dados,  
  2. analisar os dados,  
  3. manipular os dados,  
  4. empregar os algoritmos mais adequados conforme os dados disponíveis,  
  5. avaliar os resultados de cada algoritmo empregado,  
  6. apresentar os resultados finais.

Nesse artigo em particular iremos tratar dos três primeiros passos (na verdade dos dois primeiros, pois, como se verá, não será necessária nenhuma manipulação mais específica dos dados). Os demais passos, serão tratados em postagens subsequentes.

Vamos, então, à diversão e, com o Weka já aberto, clique em  **Explorer**.

image



### Carregando os dados
Nesse primeiro projeto, vamos utilizar uma das bases de dados que já vem com a instalação padrão da ferramenta. Na janela do Explorer que se abriu, clique agora em **Open file** e vá até a pasta **data/** que, por sua vez, se encontra dentro da pasta onde você instalou o Weka. No meu caso, no Linux, as bases de dados se encontram no seguinte caminho: **~/ml/weka-3-8-6/data/**.

Nesse local você encontrará vários arquivos com a extensão *.arff*. Clique em **iris.arff** e depois em **Abrir** (ou *Open*). Pronto, os dados foram carregados com suscesso e você verá uma tela semelhante à figura que se segue:

image

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