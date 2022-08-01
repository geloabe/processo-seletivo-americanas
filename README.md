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

### Análise Exploratória dos Dados
Já de início, foi informado que não haviam dados nulos, ou seja, não foi necessário tratar isso.

Como não havia muitas informações sobre a base, decidi investigar as variáveis. Analisando a quantidade de valores únicos e estatísticas básicas, cheguei a algumas observações:

1. As variáveis 'feature1' e 'feature15' aparentavam ser variáveis categóricas já codificadas;
2. Algumas variáveis possuem muitos valores repetidos (desbalanceamento);
3. Algumas variáveis estão em escalas muito diferentes;
4. Algumas variáveis aparentam ter outliers.

Sendo assim, tratei os outliers com uma técnica estatística que consiste nos seguintes passos:
