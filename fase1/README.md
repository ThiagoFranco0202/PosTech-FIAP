# Trabalho Fase 1 Turma 9IADT - Problemas Cardíacos - Grupo 86

Este notebook realiza uma análise exploratória e modelagem preditiva sobre um dataset de pacientes com problemas cardíacos, coletado de 11 clínicas em diferentes países. O objetivo é prever a presença de doença cardíaca com base em variáveis clínicas.

## Link para o Dataset

O dataset utilizado pode ser baixado em: [https://www.kaggle.com/datasets/fedesoriano/heart-failure-prediction?resource=download](https://www.kaggle.com/datasets/fedesoriano/heart-failure-prediction?resource=download)

## Instruções de Execução

1. Instale o Python no seu ambiente antes de instalar as bibliotecas.
2. O dataset utilizado já está no repositório junto com o notebook, mas caso queira optar por baixá-lo e salvá-lo em outro diretório, o arquivo `heart.csv` se encontra no link acima. Caso opte por colocar o csv em outro diretório, altere o caminho no código (`pd.read_csv('novo_diretório')`).
3. Instale as bibliotecas necessárias: `pandas`, `seaborn`, `matplotlib`, `scikit-learn`.
4. Abra o notebook `notebook.ipynb` em um ambiente Jupyter (como VS Code, Jupyter Lab ou Google Colab).
5. Execute as células em ordem sequencial ou o projeto todo de uma vez.

## Resultados Obtidos

### Modelagem e Avaliação

Foram testados três modelos de classificação: Regressão Logística, Random Forest e Gradient Boosting.

**Métricas de Performance (ordenadas por Recall)**:

| Modelo              | Accuracy | Precision | Recall | F1-score | ROC-AUC |
|---------------------|----------|-----------|--------|----------|---------|
| Logistic Regression | 0.886    | 0.886     | 0.912  | 0.899    | 0.933   |
| Random Forest       | 0.880    | 0.877     | 0.912  | 0.894    | 0.923   |
| Gradient Boosting   | 0.880    | 0.892     | 0.892  | 0.892    | 0.918   |

**Relatório de Classificação (Gradient Boosting)**:
```
              precision    recall  f1-score   support

           0       0.87      0.87      0.87        82
           1       0.89      0.89      0.89       102

    accuracy                           0.88       184
   macro avg       0.88      0.88      0.88       184
weighted avg       0.88      0.88      0.88       184
```

**Matriz de Confusão**: Visualização em heatmap mostrando acertos e erros do modelo (disponível no notebook).