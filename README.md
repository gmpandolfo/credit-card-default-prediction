# credit-card-default-prediction

# Prevenção de Inadimplência e Análise de Risco de Crédito

## Tema do Projeto  
Este projeto busca **prever a inadimplência de clientes de cartão de crédito** e realizar uma análise de risco com base em seu **histórico de pagamentos e informações financeiras**.

## Problema  
Instituições financeiras precisam antecipar **quais clientes representam maior risco de não pagamento**. A inadimplência afeta diretamente a lucratividade e aumenta o risco sistêmico do setor.

## Objetivo  
Desenvolver um modelo capaz de **identificar clientes com maior probabilidade de inadimplência no mês seguinte**, auxiliando a tomada de decisão na concessão de crédito e contribuindo para a **redução de perdas financeiras**.

---

## Link do Projeto
🔗 Github: *[credit-card-default-prediction](https://github.com/gmpandolfo/credit-card-default-prediction)*

---

## Dataset Utilizado
- **Fonte:** [Kaggle - Default of Credit Card Clients Dataset](https://www.kaggle.com/datasets/uciml/default-of-credit-card-clients-dataset)  
- **Número de registros:** 30.000  
- **Número de variáveis:** 24 (após remover a coluna `ID`)  

### Principais variáveis
- **PAY_0 a PAY_6:** histórico de pagamento (atrasos nos últimos 6 meses)  
- **LIMIT_BAL:** limite de crédito  
- **BILL_AMT1 a BILL_AMT6:** valor das faturas mensais  
- **PAY_AMT1 a PAY_AMT6:** valor dos pagamentos realizados  
- **AGE:** idade  
- **SEX:** sexo (1 = masculino, 2 = feminino)  
- **EDUCATION:** nível de educação  
- **MARRIAGE:** estado civil  

---

## Transformações Realizadas
- Remoção da coluna `ID` (não relevante).  
- Correção de valores inconsistentes nas variáveis `EDUCATION` e `MARRIAGE`.  
- Padronização dos atributos numéricos com **StandardScaler**.  
- Separação entre **features (X)** e **target (y)**.  
- Divisão do dataset em **treino (70%)** e **teste (30%)**.  

---

## Modelos de Machine Learning
Foram aplicados três modelos para classificação binária (inadimplente x não inadimplente):

1. **Logistic Regression**  
   - Modelo linear, interpretável e utilizado como baseline.  

2. **Decision Tree**  
   - Modelo baseado em regras de decisão, útil para interpretar fatores de risco.  

3. **Random Forest**  
   - Modelo de ensemble, mais robusto e com melhor performance na maioria dos casos.  

---

## Resultados Obtidos
Os modelos foram avaliados com **Accuracy, Precision, Recall, F1-score e AUC-ROC**.  

- **Logistic Regression:** boa acurácia, mas recall relativamente baixo para a classe 1 (inadimplentes).  
- **Decision Tree:** fácil de interpretar, mas apresentou maior risco de overfitting e métricas menos consistentes.  
- **Random Forest:** obteve o melhor equilíbrio geral, com boa acurácia, recall mais robusto para inadimplentes e maior AUC-ROC entre os modelos.  

👉 **Métrica mais crítica:** **Recall da classe 1 (inadimplentes)**.  
No contexto de crédito, **não identificar um inadimplente** representa maior risco financeiro do que recusar erroneamente um cliente adimplente.  

---

## Análise de Risco
- **Variáveis mais relevantes (Random Forest):**  
  - **PAY_0 (último status de pagamento)** → fator isolado mais preditivo.  
  - **Idade (AGE)** → clientes mais jovens apresentam maior frequência de inadimplência.  
  - **LIMIT_BAL (limite de crédito)** → limites mais baixos estão associados a maior risco.  
  - **BILL_AMT (valores das faturas recentes)** → ajudam a refletir a capacidade e padrão de consumo do cliente.  

---

## Conclusões
- O modelo de **Random Forest** foi o mais eficaz na previsão da inadimplência, equilibrando bem recall e acurácia.  
- O **histórico de pagamentos recentes** é o principal indicador de risco, seguido por idade e limite de crédito.  
- Este estudo pode apoiar a **decisão na concessão de crédito**, auxiliando instituições financeiras a reduzir perdas.  

Obrigado!