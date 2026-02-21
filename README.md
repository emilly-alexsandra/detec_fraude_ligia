# detec_fraude_ligia
Esse repositório é destinado ao desafio individual do processo seletivo da Liga Acadêmica de Inteligência Artificial da UFPE. O projeto implementa um modelo de Machine Learning para detecção de fraudes em transações financeiras.
---
## Autora

Emilly Alexsandra de Oliveira Silva

Acadêmica de Engenharia Biomédica - UFPE

Recife - PE

---
- ## Objetivo

Desenvolver um modelo preditivo capaz de identificar transações fraudulentas com alta precisão, lidando com forte desbalanceamento de classes e fornecendo explicações interpretáveis para as decisões do modelo.

---

- ## Metodologia
O projeto foi desenvolvido seguindo as etapas clássicas de um pipeline de Machine Learning:
1. **Pré-processamento dos dados**
   - Limpeza e tratamento de valores inconsistentes
   - Engenharia de atributos
   - Divisão treino/teste com `train_test_split`

2. **Tratamento de desbalanceamento**
   - Ajuste do parâmetro `scale_pos_weight` no XGBoost
   - Avaliação com métricas apropriadas (ROC-AUC, Recall, F1-score)

3. **Treinamento do modelo**
   - Modelo principal: `XGBoost Classifier`
   - Ajuste de hiperparâmetros
   - Validação com métricas de classificação

4. **Avaliação de desempenho**
   - Curva ROC
   - ROC-AUC Score
   - Precision, Recall e F1-score

  5. **Explainable AI**
   - SHAP values para interpretação das previsões
   - Permutation Importance para análise de relevância das features

---

## - Resultados

O modelo apresentou excelente desempenho na detecção de fraude:

| Avaliação | ROC-AUC |
|----------|--------|
| Validação Cruzada | 0.985703 ± 0.008092 |
| Hold-out | 0.977095 |
| Kaggle | 0.98718 |



| Métrica | Classe 1 (Fraude) |
|--------|------------------|
| Precision |  0.85  |
| Recall | 0.80 |
| F1-score | 0.82 |

O modelo demonstrou alta capacidade de distinguir entre classes, mesmo com forte desbalanceamento.

## - Validação e Generalização

O modelo foi avaliado utilizando duas estratégias complementares:

- **Hold-out validation:** divisão treino/teste com dados não vistos
- **Stratified K-Fold Cross-Validation (k=5):** garantindo estabilidade do desempenho em diferentes partições

Além disso, o modelo foi testado em dados externos da competição Kaggle, reforçando sua capacidade de generalização.

---
## - Interpretabilidade do Modelo

Foram utilizadas técnicas de Explainable AI para garantir transparência nas decisões do modelo:

- **SHAP (SHapley Additive Explanations):**
  - Identificação das variáveis que mais influenciam cada predição
  - Visualização global e local da importância das features

- **Permutation Importance:**
  - Avaliação da importância das variáveis baseada na perda de desempenho

---

## - Dataset

O dataset utilizado não está incluído no repositório.

Para reproduzir o projeto:

1. Baixe o dataset train.csv e test.csv no Kaggle:
   
https://www.kaggle.com/competitions/ligia-machine-learning/data?select=train.csv

2. Execute o notebook principal

---

# - Como Executar o Projeto

1. Clone o repositório:

```bash
git clone https://github.com/emilly-alexsandra/detec_fraude_ligia.git

cd detec_fraude_ligia

pip install -r requirements.txt

jupyter notebook notebooks/Desafio_Individual_emilly.ipynb

```

