# 📊 Previsão de Turnover de Colaboradores (HR Analytics)

Este projeto utiliza a metodologia **CRISP-DM** para identificar padrões de comportamento e prever a probabilidade de desligamento de funcionários. Através de técnicas de **Machine Learning**, transformo dados brutos de RH em inteligência preventiva.

---

## 🚀 Metodologia: CRISP-DM

### 1. Compreensão do Negócio
Meu objetivo é reduzir o turnover voluntário, que gera custos elevados de substituição e perda de capital intelectual. 
* **Minha Meta:** Desenvolver um modelo de classificação binária com foco em **Recall**, garantindo que o RH detecte o maior número possível de colaboradores em risco.

### 2. Compreensão dos Dados
Analisei um dataset de ~10.000 registros (2016-2020). 
* **Insight Crítico:** Identifiquei o "Paradoxo da Satisfação", onde a satisfação sozinha não separa as classes, exigindo modelos de **Ensemble (Random Forest)** para capturar interações complexas entre carga horária e performance.

### 3. Preparação dos Dados
* **Encoding:** Mapeamento ordinal para `salary` e One-Hot Encoding para `department`.
* **Estratificação:** Divisão 80/20 preservando a proporção de 29% de churn.
* **Engenharia:** Validei que o modelo baseline com pesos balanceados supera técnicas como SMOTE para este problema específico.

### 4. Modelagem e Avaliação
O modelo final (**Random Forest**) atingiu:
* **Recall de 77%:** Identifiquei corretamente 428 dos 557 desligamentos reais.
* **Precisão de 71%:** Alertas confiáveis para ação imediata do RH.
* **Principais Drivers:** 1. `review` (28%), 2. `avg_hrs_month` (27%), 3. `satisfaction` (23%).

---

## 📂 Sobre o Dataset e Créditos
Os dados foram obtidos via Kaggle, disponibilizados por **Marika Stewart**.
* **Fonte:** [Employee Turnover Dataset](https://www.kaggle.com/datasets/marikastewart/employee-turnover)
* **Licença:** [CC0: Public Domain](https://creativecommons.org/publicdomain/zero/1.0/)

---
*Projeto desenvolvido por Eduardo Lucena Alves (@Dudiesz)*
