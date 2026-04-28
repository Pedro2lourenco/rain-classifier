

# Rainfall Prediction Classifier

## Descrição

Este projeto tem como objetivo construir um modelo de machine learning capaz de prever a ocorrência de chuva com base em dados meteorológicos históricos da Austrália.

O problema é tratado como uma tarefa de **classificação supervisionada**, onde o modelo aprende padrões a partir de variáveis climáticas para prever se irá chover em um determinado dia.

---

## Objetivos

* Explorar e analisar um conjunto de dados reais
* Realizar engenharia de atributos (feature engineering)
* Construir pipelines de machine learning
* Otimizar modelos utilizando Grid Search com validação cruzada
* Avaliar o desempenho dos modelos com métricas apropriadas
* Comparar diferentes algoritmos de classificação

---

## Conjunto de Dados

O dataset utilizado contém informações meteorológicas diárias entre 2008 e 2017, incluindo variáveis como:

* Temperatura mínima e máxima
* Umidade
* Pressão atmosférica
* Velocidade e direção do vento
* Radiação solar
* Precipitação

Variável alvo:

* `RainTomorrow` (ou `RainToday` após ajuste): indica se haverá chuva (Yes/No)

Fonte dos dados:

* Bureau of Meteorology (Austrália)
* Kaggle: Weather Dataset

---

## Tecnologias Utilizadas

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn

---

## Etapas do Projeto

### 1. Importação e Preparação dos Dados

* Carregamento do dataset
* Análise inicial das variáveis
* Tratamento de valores ausentes
* Remoção de dados incompletos

### 2. Análise Exploratória

* Identificação de padrões
* Avaliação de correlações
* Visualização de dados

### 3. Engenharia de Atributos

* Codificação de variáveis categóricas
* Normalização de variáveis numéricas
* Criação de novas features relevantes

### 4. Pipeline de Machine Learning

* Uso de `Pipeline` para organizar o fluxo:

  * Pré-processamento
  * Treinamento do modelo

* Uso de `ColumnTransformer` para aplicar transformações diferentes em variáveis numéricas e categóricas

### 5. Treinamento e Otimização

* Aplicação de algoritmos de classificação
* Uso de Grid Search com validação cruzada
* Ajuste de hiperparâmetros

### 6. Avaliação do Modelo

* Métricas utilizadas:

  * Acurácia
  * Precisão
  * Recall
  * F1-score

* Interpretação dos resultados

---

## Considerações Importantes

### Data Leakage

Um dos principais desafios do projeto é evitar **vazamento de dados (data leakage)**.

Exemplo:

* Usar variáveis como `Temp3pm` ou `Humidity3pm` para prever chuva no mesmo dia pode introduzir informações que não estariam disponíveis no momento da previsão.

### Features Ineficientes

Algumas variáveis podem prejudicar o modelo:

* Datas em formato bruto (sem transformação)
* Variáveis altamente correlacionadas
* Direção do vento sem codificação adequada
* Localização com alta cardinalidade

---

## Estratégia Alternativa

Uma abordagem mais realista consiste em:

* Prever a chuva de hoje com base em dados até ontem
* Ajustar as variáveis:

  * `RainToday` → `RainYesterday`
  * `RainTomorrow` → `RainToday`

Isso evita inconsistências temporais e melhora a aplicabilidade do modelo no mundo real.

---

## Resultados Esperados

* Um modelo capaz de prever chuva com boa performance
* Pipeline reutilizável e escalável
* Melhor entendimento sobre pré-processamento e validação de modelos

---

## Instale as dependências:

```bash
pip install numpy pandas matplotlib seaborn scikit-learn
```

---

## Conclusão

Este projeto demonstra um fluxo completo de machine learning aplicado a dados reais, destacando a importância de:

* Pré-processamento adequado
* Escolha correta de features
* Evitar vazamento de dados
* Avaliação criteriosa de modelos

---

