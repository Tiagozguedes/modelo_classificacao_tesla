## 👨‍💻 Autor
**Tiago TG**  
📍 Projeto acadêmico desenvolvido para a disciplina de Inteligência Artificial Aplicada à Classificação  
🎓 FIAP – Análise e Desenvolvimento de Sistemas
RM: 564731
## GitHub
-- **https://github.com/Tiagozguedes/modelo_classificacao_tesla**

---

# 🧠 Modelo de Classificação com IA – Tesla Stock Prediction

## 📘 Descrição do Projeto
Este projeto foi desenvolvido como parte da **CP5 – Modelo de Classificação com IA** do curso de **Análise e Desenvolvimento de Sistemas (FIAP)**.  
O objetivo é aplicar um pipeline completo de **Machine Learning supervisionado** para resolver um problema real de **classificação binária**: prever se o preço da ação da **Tesla (TSLA)** irá **subir (1)** ou **cair (0)** no próximo dia.

---

## 🎯 Objetivo Geral
Desenvolver um modelo de classificação utilizando um dataset real e público, aplicando as etapas de:
- Exploração e preparação dos dados;
- Engenharia de atributos;
- Treinamento e avaliação de modelo supervisionado;
- Interpretação técnica dos resultados obtidos.

---

## 🧩 Contexto do Problema
A inteligência artificial aplicada à classificação é amplamente utilizada em áreas como:
- **Análise de mercado financeiro**,  
- **Detecção de fraudes**,  
- **Diagnóstico médico**,  
- **Análise de sentimentos** e **recomendações automatizadas**.  

Neste projeto, a classificação foi aplicada ao domínio **financeiro**, com foco em prever variações no preço das ações da Tesla, utilizando dados históricos da bolsa de valores.

---

## 📊 Dataset Utilizado
- **Fonte:** [Kaggle – Tesla Inc (TSLA) Dataset](https://www.kaggle.com/datasets/abhimaneukj/tesla-inc-tsla-dataset)
- **Tipo de dados:** Séries temporais de valores de ações
- **Atributos principais:**
  - `Date`: data da cotação  
  - `Open`, `High`, `Low`, `Close`, `Adj Close`: valores de abertura, máxima, mínima e fechamento  
  - `Volume`: quantidade de ações negociadas  

O dataset é **público e ético**, sem informações pessoais sensíveis.

---

## ⚙️ Metodologia

### 1. Exploração e preparação dos dados
- Leitura e ordenação cronológica do dataset.  
- Análise descritiva e visualização da série temporal de preços.

### 2. Engenharia de atributos
Foram criadas novas variáveis (features) que ajudam o modelo a capturar padrões de mercado:
- `return_1d`: retorno percentual diário;  
- `ma_5`, `ma_10`: médias móveis (5 e 10 dias);  
- `mom_3`: momentum (diferença de preço nos últimos 3 dias);  
- `vol_5`: volatilidade (desvio padrão do retorno);  
- `ma_ratio_5_10`: razão entre médias móveis.

A variável **alvo (`Target`)** foi definida como:
> 1 → preço de fechamento do próximo dia maior que o atual  
> 0 → preço de fechamento menor ou igual

### 3. Divisão dos dados
- Separação em **treino (80%)** e **teste (20%)**, respeitando a ordem temporal (sem embaralhar).

### 4. Treinamento
- Algoritmo utilizado: **Random Forest Classifier**  
  (n_estimators = 300, min_samples_leaf = 5, random_state = 42)

### 5. Avaliação
- **Métricas:** acurácia, precisão, recall, F1-score  
- **Visualizações:** gráfico de preço, matriz de confusão, importância das features

---

## 📈 Resultados Obtidos
- **Acurácia:** ~44%  
- **Melhor desempenho na previsão de quedas do que de altas.**
- As features mais relevantes foram:
  - `ma_ratio_5_10`
  - `return_1d`
  - `Volume`
  - `vol_5`

Esses resultados refletem a **alta volatilidade** e **padrões não lineares** do mercado financeiro, exigindo abordagens mais sofisticadas para ganhos de performance.

---

## 🧠 Conclusão
O modelo demonstrou a aplicação prática de um **pipeline completo de classificação supervisionada**, com foco em previsão de comportamento financeiro.  
Apesar da acurácia moderada, o experimento mostra o potencial do uso de **IA e análise de dados** para tomada de decisão e investigação de tendências.

### Possíveis melhorias:
- Adicionar indicadores técnicos (RSI, MACD, EMA);
- Usar algoritmos mais avançados (XGBoost, LSTM);
- Testar diferentes janelas temporais e validação cruzada por blocos.

---

## 🛠️ Tecnologias Utilizadas
- **Python 3.12**
- **Pandas**
- **NumPy**
- **Matplotlib**
- **Scikit-learn**
- **Jupyter Notebook / VS Code**


