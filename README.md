# Projeto-8-MLops

# 🚀 Projeto de MLOps com Gaussian Naive Bayes

Este repositório apresenta um pipeline completo de MLOps (Machine Learning Operations), cobrindo desde a preparação dos dados até o deploy e monitoramento de um modelo de machine learning em produção.

---

## 📌 Objetivo

Automatizar e escalar o ciclo de vida de um modelo Gaussian Naive Bayes com hiperparâmetros utilizando práticas modernas de MLOps, como versionamento de modelos, rastreamento de experimentos, deployment via API e reprodutibilidade dos resultados.

---

## ⚙️ Tecnologias e Ferramentas Utilizadas

- **Python**  
- **MLflow**: Rastreio de experimentos, registro e deploy de modelos de machine learning.
- **MLflow.sklearn**: Integração entre o Scikit-learn e o MLflow para log e salvamento de modelos.
- **Scikit-learn**: Treinamento de modelos (Naive Bayes), avaliação (acurácia, F1-score, AUC, etc.) e divisão dos dados com `train_test_split`.
- **Pandas**: Leitura, manipulação e análise de dados em formato tabular (DataFrames).
- **NumPy**: Operações matemáticas e manipulação de arrays numéricos.
- **Matplotlib**: Visualização de dados e gráficos como curva ROC e matriz de confusão.
- **Seaborn**: Criação de visualizações estatísticas mais elaboradas (como heatmaps).
- **Requests**: Fazer requisições HTTP

Essas tecnologias cobrem todo o pipeline de machine learning: da preparação de dados à modelagem, avaliação, visualização e deploy com MLflow.

---

## 🧠 Etapas do Pipeline MLOps

1. **📊 Análise e Preparação dos Dados**
   - Coleta, limpeza e transformação dos dados.
   - Divisão em conjuntos de treino e teste.

2. **🏗️ Treinamento do Modelo**
   - Escolha do algoritmo Gaussian Naive Bayes
   - Definição de hiperparâmetros var_smoothing para evitar problemas de probabilidade zero e melhorar a generalização do modelo.
   - Registro dos experimentos no MLflow (parâmetros, métricas e artefatos).

3. **📦 Versionamento e Registro**
   - Registro do modelo no MLflow.

4. **🚀 Deploy do modelo**
   - Modelo de machine learning disponibilizado localmente como serviço via MLflow, com endpoint HTTP para previsões. A aplicação permite consumo externo por meio de requisições REST.

5. **📈 Monitoramento e Reavaliação**
   - Estrutura para revalidação periódica do modelo com novos dados.
   - Logging (registro) de métricas de produção

---

## ✅ Resultados

O modelo modelo alcançou os seguintes resultados nos dados de teste:

| Métrica    | Valor                |
|------------|----------------------|
| Acurácia   | 0.6967               |
| AUC        | 0.6600               |
| F1 Score   | 0.7719               |
| Log Loss   | 10.9332              |
| Precisão   | 0.7739               |
| Recall     | 0.7700               |

 - Acurácia (~69,7%): modelo acerta quase 7 em cada 10 previsões.
 - AUC (0,66): capacidade moderada de distinguir entre classes.
 - F1 Score (0,77): bom equilíbrio entre precisão e recall.
 - Precisão (0,77): entre as previsões positivas, 77% são corretas (baixo falso positivo).
 - Recall (0,77): o modelo identifica 77% dos casos positivos reais (baixo falso negativo).
 - Log Loss (10,93): relativamente alto, indicando que as probabilidades previstas podem não ser muito confiáveis.

