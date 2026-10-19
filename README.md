# Customer Repurchase Prediction

Projeto de Machine Learning aplicado ao varejo para prever se um cliente realizará uma nova compra, utilizando dados históricos de transações e comportamento de consumo.

## Objetivo do projeto

Desenvolver um modelo de classificação capaz de identificar clientes com maior probabilidade de recompra, gerando informações que possam apoiar estratégias de relacionamento e marketing.

## Fonte dos dados

- **Dataset:** Online Retail
- **Fonte:** UCI Machine Learning Repository
- **Link:** https://archive.ics.uci.edu/dataset/352/online+retail
- **Período:** dezembro de 2010 a dezembro de 2011

## Problema de Machine Learning

O objetivo é prever se um cliente realizou pelo menos uma compra em novembro de 2011.

- `repurchased = 1`: cliente realizou uma compra no período.
- `repurchased = 0`: cliente não realizou uma compra no período.

O problema foi definido como uma tarefa de **classificação binária supervisionada**.

## Tecnologias utilizadas

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- Google Colab

## Features utilizadas

| Variável | Descrição |
|---|---|
| `recency_days` | Dias desde a última compra até a data de referência |
| `frequency` | Quantidade de faturas distintas no período analisado |
| `monetary_value` | Valor total das compras válidas no período |
| `repurchased` | Target: indica se o cliente voltou a comprar |

As features seguem o conceito de RFM (Recency, Frequency e Monetary Value).

## Etapas do projeto

1. Carregamento e exploração dos dados.
2. Análise de tipos de dados e valores ausentes.
3. Tratamento de registros sem identificador de cliente.
4. Identificação de cancelamentos e remoção de linhas inválidas para a análise.
5. Criação das variáveis de comportamento de compra.
6. Construção do target de recompra.
7. Separação dos dados em treino e teste.
8. Treinamento de modelos de classificação.
9. Comparação dos resultados com um baseline.
10. Avaliação por métricas e matriz de confusão.

## Modelos avaliados

- Decision Tree
- Random Forest
- Dummy Classifier (baseline)

## Resultados iniciais

Resultados obtidos no conjunto de teste:

| Métrica | Random Forest |
|---|---:|
| Acurácia | 68,55% |
| Precisão | 53,19% |
| Recall | 55,97% |
| F1-score | 54,55% |
| ROC-AUC | 71,72% |

O Random Forest apresentou ROC-AUC de 0,7172, indicando capacidade de distinguir as classes acima do acaso neste conjunto de teste.

O recall de 55,97% mostra que o modelo identificou pouco mais da metade dos clientes que efetivamente voltaram a comprar. Os resultados são iniciais e ainda precisam de validação adicional.

## Importância das features

No modelo Random Forest, as importâncias estimadas foram:

- `monetary_value`: 42,61%
- `recency_days`: 34,10%
- `frequency`: 23,29%

Essas importâncias indicam como as variáveis contribuíram para as decisões do modelo. Não demonstram causalidade nem garantem que a mesma ordem se mantenha em outros dados.

## Limitações

- A base representa um único varejista e um período histórico específico.
- A ausência de recompra em um mês não significa necessariamente abandono do cliente.
- O tratamento de cancelamentos e devoluções pode influenciar os resultados.
- A avaliação utiliza uma única divisão entre treino e teste.
- O desempenho ainda precisa ser validado em outros períodos antes de qualquer aplicação operacional.

## Próximas melhorias

- Realizar validação temporal.
- Comparar diferentes modelos e parâmetros.
- Avaliar outras métricas e limiares de classificação.
- Investigar o impacto de cancelamentos e devoluções.
- Desenvolver recomendações de negócio com base nos resultados.

## Estrutura dos arquivos

- `Customer_Repurchase_Prediction.ipynb`: notebook com o código e as análises.
- `customer_repurchase_dataset.csv`: base preparada para modelagem.
- `model_comparison.csv`: comparação entre modelos.
- `final_metrics.csv`: métricas finais.
- `customer_repurchase_model.pkl`: modelo treinado exportado.

## Conclusão

Este projeto foi desenvolvido para aplicar conceitos de análise de dados e Machine Learning a um problema de negócio do varejo, desde a preparação dos dados até a avaliação de modelos de classificação.

O trabalho reforça a importância de combinar conhecimento técnico, métricas adequadas e entendimento do contexto de negócio para desenvolver soluções analíticas responsáveis.

**Projeto de portfólio — Machine Learning aplicado ao varejo.**

### Atribuição dos dados

Dados disponibilizados pelo UCI Machine Learning Repository: Online Retail. Consulte a [página oficial do dataset](https://archive.ics.uci.edu/dataset/352/online+retail) para detalhes sobre a licença e atribuição.
