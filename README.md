# Teste Cognitivo.ai Classificação Room Type

**a. Como foi a definição da sua estratégia de modelagem?**

Inicialmente foi realizada a sumarização, descrição e análise dos dados. Então, foram geradas novas features por meio da categorização das variáveis `availability_365`, `number_of_reviews` e `price` associada a variável `neighbourhood`. Todo o processo de engenharia de features foi detalhado no notebook.

A partir disso, foi realizado a normalização das features numéricas que apresentaram distribuição não Gaussiana. Depois, foi feito o balanceamento de classes da variável alvo `room_type`, a fim de reduzir um possível enviesamento dos modelos.

Os dados foram divididos em treino e teste, respeitando a proporção 75% e 25% respectivamente. Para o treinamento e tuning dos modelos utilizamos a técnica de validação cruzada com 5 k-folds.

**b. Como foi definida a função de custo utilizada?**

Para o problema de classificação em questão o custo de classificar uma dada entrada erroneamente é alto tanto para falso-positivos quanto para falso-negativos. Neste caso definimos a função de custo como sendo o f1-score, uma vez que a métrica harmoniza *Precission* e *Recall*. 

**c. Qual foi o critério utilizado na seleção do modelo final?**

Foram utilizados os modelos mais conhecidos e amplamente empregados em tarefas de classificação. O modelo final escolhido foi aquele que obteve o melhor valor para função de custo definida (f1-score) na predição do conjunto de teste.

**d. Qual foi o critério utilizado para validação do modelo? Por que escolheu utilizar este método?**

Inicialmente treinamos os modelos com os dados de treino utilizando a técnica de validação cruzada, a fim de determinar os melhores hiperparametros para cada um deles. Então treinamos os modelos com todos dados do conjunto de treino, dessa vez utilizando o melhor hiperparamentro encontrado para cada um. Por fim, realizamos a predição dos dados de teste estimando seus respectivos valores de f1-score.

A seleção do método utilizado se justifica por meio da priorização da análise de *overfitting* e capacidade de generalização dos modelos. Uma vez que, modelos que apresentariam *overfitting* tem uma redução significativa do f1-score ao predizer o conjunto de teste, devido ao super ajuste aos dados de treino. Isso também impactaria diretamente na capacidade de generalização dos modelos.

**e. Quais evidências você possui de que seu modelo é suficientemente bom?**

Considerando que, em regra, todos os modelos apresentaram uma variação pequena do f1-score obtido no treino e teste, sugerindo que os modelos tem boa capacidade de generalização (pouco ajuste aos dados), assim capturando bem as caracteristicas da função geratriz (natureza) dos dados.
