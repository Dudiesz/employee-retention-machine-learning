# 📊 Previsão de Turnover de Colaboradores (HR Analytics)

Este projeto aplica a metodologia **CRISP-DM** para identificar padrões de comportamento e prever a probabilidade de desligamento de funcionários em uma grande empresa dos EUA. Utilizei técnicas de **Machine Learning** para transformar dados de RH em insights acionáveis que permitem intervenções preventivas.

---

## 🚀 Metodologia: CRISP-DM

### 1. Compreensão do Negócio
Meu objetivo principal é reduzir o turnover voluntário, que gera custos elevados de substituição e perda de capital intelectual. 
* **Minha Meta Técnica:** Desenvolver um modelo de classificação binária com foco em **Recall**, garantindo que o RH detecte o maior número possível de colaboradores em risco.

### 2. Compreensão dos Dados
Analisei um dataset de aproximadamente 10.000 registros (2016-2020). 
* **Descoberta Crítica:** Identifiquei o "Paradoxo da Satisfação", onde a mediana de satisfação entre quem sai e quem fica é similar. Isso me levou a descartar modelos lineares simples em favor de modelos baseados em **Ensembles (Árvores)**, capazes de capturar interações complexas.

### 3. Preparação dos Dados
Realizei o tratamento completo dos dados para garantir a performance do modelo:
* **Encoding:** Mapeamento ordinal para `salary` e One-Hot Encoding para `department`.
* **Estratificação:** Divisão 80/20 mantendo a proporção de 29% de churn em ambos os conjuntos.
* **Engenharia de Atributos:** Explorei interações entre carga horária, satisfação e tempo de casa.

### 4. Modelagem e Otimização
Testei diversas abordagens para encontrar o melhor equilíbrio:
1.  **Random Forest (Baseline):** Utilizei `class_weight='balanced'` para lidar com o desbalanceamento.
2.  **Tuning:** Realizei busca de hiperparâmetros via `RandomizedSearchCV`.
3.  **Técnicas Avançadas:** Experimentei **SMOTE** e **Threshold Tuning** para tentar elevar o Recall.
* **Resultado:** O modelo Random Forest Baseline provou ser o mais estável e confiável para os objetivos de negócio.

### 5. Avaliação (Impacto Real)
O modelo final atingiu um desempenho sólido:
* **Recall de 77%:** Identifiquei corretamente 428 dos 557 desligamentos no conjunto de teste.
* **Precisão de 71%:** Garanti que os alertas do modelo sejam confiáveis o suficiente para o RH agir.

**Principais Drivers de Saída (Feature Importance):**
1.  **Review (28%):** Avaliações de desempenho são o maior preditor.
2.  **Average Monthly Hours (27%):** Carga horária excessiva está diretamente ligada ao churn.
3.  **Satisfaction (23%):** O sentimento do colaborador completa a tríade de decisão.

---

## 🛠️ Tecnologias Utilizadas
* **Linguagem:** Python
* **Bibliotecas:** Pandas, Scikit-learn, Matplotlib, Seaborn, Imbalanced-learn
* **Metodologia:** CRISP-DM

---

## 📈 Conclusões de Negócio
Através deste projeto, entrego ao RH não apenas um arquivo de predições, mas uma estratégia:
* **Ações Proativas:** Focar em "Stay Interviews" com o grupo de risco identificado.
* **Políticas de Bem-estar:** Revisar a distribuição de carga horária (burnout) em departamentos críticos.
* **Retenção de Talentos:** Criar planos de carreira para colaboradores com alto desempenho (`review`) que apresentam sinais de queda na satisfação.

---
*Projeto desenvolvido por Eduardo Lucena Alves (@Dudiesz)*
