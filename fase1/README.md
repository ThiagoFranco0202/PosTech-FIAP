# Trabalho Fase 1 Turma 9IADT - Problemas Cardíacos - Grupo 86

Este projeto realiza uma análise exploratória e uma modelagem preditiva sobre um dataset de pacientes com informações clínicas relacionadas a problemas cardíacos. O objetivo é prever a presença ou ausência de doença cardíaca com base nas variáveis disponíveis na base.

## Link para o Dataset

O dataset utilizado pode ser baixado em: [Heart Failure Prediction Dataset - Kaggle](https://www.kaggle.com/datasets/fedesoriano/heart-failure-prediction?resource=download)

## Objetivo do Projeto

O objetivo principal é construir e comparar modelos de classificação capazes de identificar possíveis casos de doença cardíaca a partir de atributos clínicos dos pacientes.

Como se trata de um problema relacionado à saúde, a análise das métricas considera especialmente o **Recall**, pois é importante reduzir falsos negativos, ou seja, evitar que pacientes com possível doença cardíaca sejam classificados incorretamente como saudáveis.

## Instruções de Execução

1. Instale o Python no ambiente de execução.
2. Instale as bibliotecas necessárias:

```bash
pip install pandas seaborn matplotlib scikit-learn
```

3. Certifique-se de que o arquivo `heart.csv` esteja no mesmo diretório do notebook.
4. Abra o notebook em um ambiente Jupyter, como VS Code, Jupyter Lab ou Google Colab.
5. Execute as células em ordem sequencial.

## Dataset

A base contém informações clínicas dos pacientes, incluindo variáveis numéricas, categóricas e binárias. A variável alvo utilizada no modelo é:

- `HeartDisease`: indica a presença ou ausência de doença cardíaca.

Durante o pré-processamento, foram tratados valores inconsistentes nas colunas `Cholesterol` e `RestingBP`, substituindo valores iguais a zero pela mediana da respectiva coluna. Essa abordagem foi utilizada porque valores zero nessas variáveis não representam medidas clínicas válidas.

## Modelos Avaliados

Foram testados três modelos de classificação:

1. **Logistic Regression**
2. **Random Forest**
3. **Gradient Boosting**

A escolha desses modelos permitiu comparar abordagens com diferentes níveis de complexidade:

- A **Logistic Regression** foi usada como modelo mais simples, interpretável e adequado para classificação binária.
- O **Random Forest** foi usado por ser um modelo baseado em múltiplas árvores de decisão, capaz de capturar relações não lineares.
- O **Gradient Boosting** foi usado por ser uma técnica mais sofisticada, que cria árvores de forma sequencial para corrigir erros dos modelos anteriores.

## Resultados Obtidos

### Métricas de Performance

| Modelo              | Accuracy | Precision | Recall | F1-score | ROC-AUC |
|---------------------|----------|-----------|--------|----------|---------|
| Logistic Regression | 0.886    | 0.886     | 0.912  | 0.899    | 0.933   |
| Random Forest       | 0.880    | 0.877     | 0.912  | 0.894    | 0.923   |
| Gradient Boosting   | 0.880    | 0.892     | 0.892  | 0.892    | 0.918   |

## Melhor Modelo Escolhido

Com base nos resultados obtidos, o melhor modelo para este trabalho foi a **Logistic Regression**.

Apesar de ser um modelo mais simples, a Regressão Logística apresentou o melhor desempenho geral entre os três modelos avaliados. Ela obteve os maiores valores de **Accuracy**, **F1-score** e **ROC-AUC**, além de empatar com o Random Forest no **Recall**.

Em problemas relacionados à identificação de doença cardíaca, o **Recall** é uma métrica muito importante, pois mede a capacidade do modelo de identificar corretamente os pacientes que realmente possuem a doença. Um Recall maior ajuda a reduzir falsos negativos, que são casos em que o modelo classifica um paciente como saudável quando, na realidade, ele possui doença cardíaca.

Portanto, a Logistic Regression foi considerada a melhor escolha porque apresentou um bom equilíbrio entre simplicidade, interpretabilidade e desempenho preditivo.

## Relatório de Classificação - Logistic Regression

```text
              precision    recall  f1-score   support

           0       0.89      0.85      0.87        82
           1       0.89      0.91      0.90       102

    accuracy                           0.89       184
   macro avg       0.89      0.88      0.88       184
weighted avg       0.89      0.89      0.89       184
```

## Matriz de Confusão - Logistic Regression

```text
[[70 12]
 [ 9 93]]
```

Interpretação da matriz de confusão:

- **70** pacientes sem doença cardíaca foram classificados corretamente.
- **93** pacientes com doença cardíaca foram classificados corretamente.
- **12** pacientes foram classificados como tendo doença cardíaca, mas não tinham.
- **9** pacientes tinham doença cardíaca, mas foram classificados como não tendo.

O ponto mais importante é que o modelo apresentou **9 falsos negativos**, indicando que identificou corretamente **93 dos 102 pacientes com doença cardíaca**. Esse resultado é relevante no contexto de saúde, pois mostra boa capacidade de detectar casos positivos e reduz o risco de classificar pacientes doentes como saudáveis.

## Conclusão

A comparação entre os modelos mostrou que a **Logistic Regression** foi a opção mais adequada para a base utilizada. Embora o Random Forest tenha empatado no Recall e o Gradient Boosting tenha apresentado boa Precision, a Logistic Regression teve melhor desempenho geral, com maior Accuracy, F1-score e ROC-AUC.

Assim, para este trabalho, a Regressão Logística se destacou por combinar bom desempenho, simplicidade e maior facilidade de interpretação dos resultados.
