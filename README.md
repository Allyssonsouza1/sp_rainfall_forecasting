# sp_rainfall_forecasting
# Previsão de Chuvas em São Paulo: Análise de Séries Temporais

## Sobre o Projeto

A gestão de recursos hídricos é um desafio crítico no estado de São Paulo. Este projeto utiliza técnicas de Ciência de Dados para analisar o histórico pluviométrico do estado e prever volumes de chuvas, auxiliando na antecipação de eventos extremos (secas ou enchentes).

O estudo compara o desempenho de modelos lineares clássicos contra modelos que consideram a sazonalidade, demonstrando estatisticamente qual abordagem é mais segura para o planeamento hidrológico.

## Fonte de Dados

Os dados foram extraídos do *Banco de Dados Hidrológicos* oficial do Estado de São Paulo.

* *Fonte:* [DAEE - Departamento de Águas e Energia Elétrica](https://hidrologia.spaguas.sp.gov.br/)
* *Período analisado:* 1985 a 2021 (Histórico Mensal)
* *Localização:* Estado de São Paulo, Brasil

## Tecnologias e Ferramentas

| Categoria | Tecnologias Utilizadas |
| :--- | :--- |
| *Linguagem* | Python |
| *Manipulação* | Pandas, Numpy |
| *Visualização* | Matplotlib, Seaborn |
| *Modelagem* | Statsmodels, Pmdarima (Auto-ARIMA), Scikit-learn |

## Metodologia e Conceitos

O projeto seguiu um pipeline rigoroso de análise de séries temporais:

1.  *EDA (Análise Exploratória):* Decomposição da série em Tendência, Sazonalidade e Resíduo.
2.  *Testes de Estacionariedade:* KPSS (Kwiatkowski-Phillips-Schmidt-Shin)
3.  *Modelagem Preditiva:* Treino e teste de 5 arquiteturas:
    * *Autoregressive (AR)* 
    * *Moving Average (MA)* 
    * *Autoregressive Moving Average (ARMA)*  
    * *Autoregressive Integrated Moving Average (ARIMA)*   
    * *Seasonal Autoregressive Integrated Moving Average (SARIMA)*  

4.  *Avaliação:* Comparação via métricas de erro (RMSE, MAE) e critério de informação (AIC).

## Resultados Alcançados

O modelo *SARIMA* provou ser superior, especialmente na previsão de picos de chuva (eventos extremos), onde modelos simples falharam.

| Modelo | RMSE (Erro Médio) | Análise |
| :--- | :--- | :--- |
| *SARIMA* | *59.63* | Único capaz de capturar a sazonalidade e picos de janeiro. |
| *ARMA* | 76.61 | Bom desempenho geral, mas conservador nos picos. |
| *ARIMA* | 106.90 | Perda de performance devido à diferenciação excessiva. |
| *AR* | 111.12 | Instável para meses de alta volatilidade. |


## 📂 Estrutura do Repositório

```text
├── data/                # Bases de dados 
├── notebooks/           # Jupyter Notebooks 
├── requirements.txt     # Dependências do projeto
└── README.md            # Documentação
