Como foi a definição da sua estratégia de modelagem?
A estratégia de modelagem foi definida de acordo com a avaliação do problema em questão e posterior avaliação da variável
resposta (room_type). A variável apresenta 4 categorias, apesar de duas delas apresentarem percentuais bem baixos, resolvi
considerá-las por não ter o contexto do negócio. No contexto do atual problema, não poderia desconsiderá-las por não
saber se seriam categorias importantes para o negócio.

Como foi definida a função de custo utilizada?
A função custo foi desenhada para conforme a função softmax, utilizando as principais e agregadoras features para explicá-la.

Qual foi o critério utilizado na seleção do modelo final?
A seleção do modelo final foi primeiramente baseada na seleção de features que não houvessem qualquer tipo de vazamento
de informação sobre o alvo. No segundo momento, foram retiradas variável que possuíssem alta correlação. A partir desse ponto,
foi escolhido um algoritmo confiável de boa performance para o problema em questão (XGBoost). Por fim, foi realizado 
o cross-validation para assegura os melhores parâmetros para o modelo.

Qual foi o critério utilizado para validação do modelo? Por que escolheu utilizar este método?
Para validação do modelo foram criadas bases de treinamento e teste para assegurar a performance e afastar overfiting.
Parâmetros de classificação precision, recall, f1-score e accuracy foram levados em consideração, também avaliando
a própria matriz de confusão. Por fim, foram avaliados os rocs para esse tipo de problemática (ovo e ovr), demostrando
que não possui overfiting no modelo e ratificando que o treinamento e teste possuim alinhamento.

Quais evidências você possui de que seu modelo é suficientemente bom?
Primeiramente, pela construção de uma visão expansiva que trouxe features relevantes para o modelo, removendo variáveis
com anomalias de preenchimento nulo e de correlação exarcebada. Segundo, pela metodologia baseada nas boas práticas do 
mercado, utilizando o sklearn (infelizmente, pelo tempo não consegui seguir toda a metologia de pipeline adotada por eles).
Terceiro, pelo uso de um algoritmo sabidamente eficiente para o tipo de problematica abordada. Quarto, pelo uso do cross-validation
para tunar os parâmetros do algoritmo. Por fim, pelas métricas obitidas do modelo, referendando o bom desempenho.