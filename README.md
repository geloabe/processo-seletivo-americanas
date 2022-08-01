<h1> Processo seletivo | Cientista de Dados Jr | Americanas S.A. </h1>

Tabela de conteúdos
=================
<!--ts-->
   * [Pré-requisitos](#pre-requisitos)
   * [Análise Exploratória dos Dados](#analise-exploratoria)
   * [Modelagem](#modelagem)
   * [Otimização](#otimizacao)
<!--te-->

### Pré-requisitos
Para executar a solução, é necessário ter uma ferramenta que comporte Jupyter Notebooks do Python. como Google Colab ou Anaconda. Também é necessário instalar as bibliotecas e suas versões específicas, que estão listadas no arquivo requirements.txt. Para isso, basta executar o comando "pip install requirements.txt" no terminal, utilizando um ambiente virtual Python, ou "conda install requirements.txt", no caso de utilizar o ambiente anaconda.

A solução está contida no arquivo "notebook.ipynb". Basta baixar os arquivos do repositório e executar os scripts.

### Análise Exploratória dos Dados
Já de início, foi informado que não haviam dados nulos, ou seja, não foi necessário tratar isso.

#### Análise univariada
Como não havia muitas informações sobre a base, decidi investigar as variáveis. Analisando a quantidade de valores únicos e estatísticas básicas, cheguei a algumas observações:

1. As variáveis 'feature1' e 'feature15' aparentavam ser variáveis categóricas já codificadas;
2. Algumas variáveis possuem muitos valores repetidos (desbalanceamento);
3. Algumas variáveis estão em escalas muito diferentes;
4. Algumas variáveis aparentam ter outliers.

#### Análise e tratamento de outliers
Sendo assim, tratei os outliers com uma técnica estatística que consiste nos seguintes passos. Para cada variável numérica:
1. Descobrir o Intervalo Interquartil;
2. Calcular os limites superior e inferior;
3. Verificar quais dados estão além desses limites e classificá-los como outliers.

Optei por simplesmente excluir esses outliers da base de dados. Após isso, verifiquei a distribuição dos dados e observei que as features não são normalmente distribuídas.

#### Análise multivariada
Como não há informações sobre as variáveis da base, não há como criar hipótese de relação entre pares de variáveis. Sendo assim, analisei apenas a matriz de correlação para constatar que há multicolinearidade, devido a algumas variáveis.

### Modelagem
Na etapa de modelagem, criei um modelo base utilizando a Regressão Logística e comparei sua performance com a dos algoritmos classificador SVM e XGBoost.

Optei por avaliar os modelos utilizando a métrica de acurácia, pois as classes estão bem balanceadas e porque é uma métrica fácil de ser interpretada. Se houvesse desbalanceamento nas classes ou uma importância maior de prever a classe positiva ou a classe negativa, poderia utilizar outras métricas como recall ou precisão.

A conclusão foi que o algoritmo com melhor performance foi o SVM, porém, ainda assim, com acurácia baixa.

### Otimização
Na etapa de otimização, investigamos formas de melhorar a performance do modelo e, para isso, temos duas opções: melhorar os dados ou melhorar o modelo.

Realizei duas operações para tentar melhorar o SVM: a normalização dos dados e a redução de dimensionalidade utilizando o PCA. Nenhuma dessas etapas apresentou uma mudança significativa na acurácia do modelo.
