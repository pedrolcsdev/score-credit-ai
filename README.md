# Score Credit AI

Projeto prático e acadêmico de aprendizado de máquina para prever o score de crédito de clientes a partir de informações financeiras e comportamentais.

O objetivo é treinar modelos de classificação capazes de analisar dados históricos de clientes e estimar automaticamente a categoria de score de crédito, como `Poor`, `Standard` ou `Good`.

## Sobre o projeto

Este projeto simula um cenário em que um banco deseja classificar o perfil de crédito de seus clientes com base em dados como salário anual, número de contas, número de cartões, atrasos em pagamentos, histórico de crédito, dívidas, empréstimos e comportamento de pagamento.

O desenvolvimento foi feito em um notebook Jupyter, seguindo um fluxo básico de ciência de dados:

1. Importação da base de clientes.
2. Análise inicial dos dados.
3. Tratamento de colunas categóricas.
4. Separação dos dados em treino e teste.
5. Treinamento de modelos de machine learning.
6. Avaliação da acurácia dos modelos.
7. Previsão do score para novos clientes.

## Tecnologias utilizadas

- Python
- Pandas
- Scikit-learn
- Jupyter Notebook

## Modelos utilizados

Foram testados dois modelos de classificação:

- Random Forest Classifier
- K-Nearest Neighbors (KNN)

No teste realizado no notebook, o modelo Random Forest apresentou melhor desempenho:

| Modelo | Acurácia |
| --- | ---: |
| Random Forest | 82,47% |
| KNN | 73,24% |

Por isso, o Random Forest foi utilizado para fazer as previsões dos novos clientes.

## Estrutura do projeto

```text
score-credit-ai/
+-- clientes.csv
+-- novos_clientes.csv
+-- pratica.ipynb
+-- README.md
```

## Arquivos

- `clientes.csv`: base principal usada para treinar e testar os modelos.
- `novos_clientes.csv`: base com clientes sem score informado, usada para simular novas previsões.
- `pratica.ipynb`: notebook com todo o processo de análise, treinamento, avaliação e previsão.

## Base de dados

A base principal possui 100.000 registros e 25 colunas. A variável que o modelo tenta prever é:

- `score_credito`

Algumas variáveis usadas como entrada para o modelo são:

- `idade`
- `profissao`
- `salario_anual`
- `num_contas`
- `num_cartoes`
- `dias_atraso`
- `num_pagamentos_atrasados`
- `mix_credito`
- `divida_total`
- `taxa_uso_credito`
- `idade_historico_credito`
- `comportamento_pagamento`
- `saldo_final_mes`
- informações sobre tipos de empréstimo

As colunas textuais `profissao`, `mix_credito` e `comportamento_pagamento` foram convertidas em valores numéricos usando `LabelEncoder`, permitindo que os modelos conseguissem processar esses dados.

## Como executar

1. Clone ou baixe este repositório.
2. Instale as dependências necessárias:

```bash
pip install pandas scikit-learn notebook
```

3. Abra o Jupyter Notebook:

```bash
jupyter notebook
```

4. Execute o arquivo `pratica.ipynb` célula por célula.

## Resultado das previsões

Após o treinamento, o modelo Random Forest foi usado para prever o score de crédito dos clientes presentes em `novos_clientes.csv`.

As previsões obtidas no notebook foram:

```text
['Poor', 'Poor', 'Standard']
```

## Aprendizados

Este projeto foi desenvolvido com finalidade acadêmica e serviu como prática introdutória em aprendizado de máquina. Os principais conceitos trabalhados foram:

- leitura e manipulação de dados com Pandas;
- preparação de variáveis categóricas;
- separação entre dados de treino e teste;
- criação e treinamento de modelos de classificação;
- comparação de modelos usando acurácia;
- aplicação do modelo treinado em novos dados.

## Possíveis melhorias

- Normalizar os dados antes do uso do KNN.
- Avaliar os modelos com outras métricas, como matriz de confusão, precisão, recall e F1-score.
- Testar outros algoritmos de classificação.
- Ajustar hiperparâmetros dos modelos.
- Salvar o modelo treinado para reutilização futura.
- Criar uma interface simples para informar dados de novos clientes e receber a previsão.

## Observação

Este projeto tem fins educacionais e não deve ser usado como ferramenta real de decisão de crédito sem validação técnica, estatística e regulatória adequada.
