# Projeto Final da Disciplina Mineração de Textos e Web Ministrada pelo Prof. Luciano Barbosa (CIn-UFPE)
### Equipe: 
David Soares do Monte & Wanderson Rodrigues Marques

![facebook-g5244daba1_1920](https://user-images.githubusercontent.com/91763957/186176725-918f6a59-641d-4485-bcf4-6dad35b92bc9.jpg)

## Link para o Vídeo com a Apresentação do Projeto

https://drive.google.com/file/d/1o_9X5Q60TD-Mq9FwR33aZJyVFmxy0q-u/view?usp=sharing

Acessar com a conta "@cin.ufpe.br".

## Link para o Dashboard Desenvolvido

https://public.tableau.com/views/MonitoramentodeReviews/Dashboard1?:language=en-US&:display_count=n&:origin=viz_share_link

## Descrição do Repositório
1. Pasta `Apresentação`
<br> Contém um vídeo de aproximadamente 15 minutos no qual é feito a apresentação do projeto desenvolvido.

2. Pasta `Notebooks`
<br> Contém os notebooks utilizados no desenvolvimento do projeto, assim listados:
    * 220401_NLP_final_project_data_acquisition.ipynb
    * 220401_NLP_final_project_without_stemming.ipynb
    * 220401_NLP_final_project_with_stemming.ipynb
    * 220401_NLP_final_project_bert.ipynb

    <br> Pontos importantes:
    * O arquivo `220401_NLP_final_project_data_acquisition.ipynb` refere-se ao script utilizado para aquisição dos dados para compor o dataset utilizado no projeto;   
    * A última seção do arquivo `220401_NLP_final_project_without_stemming` contém um resumo de todas as métricas obtidas para os classificadores utilizados no projeto;
    * Excetuando-se a utilização de `stemming`, o passo-a-passo desenvolvido nos notebooks `220401_NLP_final_project_without_stemming.ipynb` e `220401_NLP_final_project_with_stemming.ipynb` é extamente o mesmo, porém o primeiro apresenta uma descrição mais detalhada das etapas adotadas no desenvolvimento do projeto;
    * O arquivo `220401_NLP_final_project_bert.ipynb` refere-se exclusivamente ao BERT.

3. Pasta `dataset`
<br> Contém o dataset utilizado no projeto.

## Descrição do Projeto
O projeto desenvolvido teve a seguinte temática: Construção de um Sistema de Monitoramento de Reviews, e consistiu das seguintes etapas:

1. Seleção de um produto a ser monitorado;
2. Coleta de reviews de sites de e-commerce do produto selecionado, incluindo as seguintes informações:
    * Conteúdo do review;
    * Estrelas de avaliação;
    * Data do review.
3. Criação de classificador de sentimentos utilizando os seguintes critérios:
    * Random Forest com bag-of-words;
    * Redes: CNN, LSTM e BERT;
    * Pré-processamento: com e sem stemming;
    * Métricas de avaliação: F1, precision e recall.
4. Construção de frontend contendo itens como:
    * Plot de reviews positivos e negativos no tempo;
    * Word cloud dos reviews;
    * Reviews mais representativos.

O frontend desenvolvido encontra-se disponível no seguinte endereço:
https://public.tableau.com/views/MonitoramentodeReviews/Dashboard1?:language=en-US&:display_count=n&:origin=viz_share_link

## Etapas de Desenvolvimento do Projeto
* **Etapa 0**: Coleta das Reviews
  * Seleção do produto;
  * Coleta das reviews.
* **Etapa 1**: Dataset
  * Informações sobre o dataset
  * Importação das Bibliotecas Necessárias
  * Importação e Pré-processamento do Dataset
* **Etapa 2**: Processamento dos Dados Textuais
  * Importação das Bibliotecas Necessárias
  * Tokenização das Sentenças
  * Importação das Bibliotecas Necessárias
  * Tokenização e Construção do Dicionário de Palavras
* **Etapa 3**: Implementação dos Classificadores
  * Importação de Bibliotecas Necessárias
  * Pré-processamento
  * Agrupamento para Identificação das Reviews mais Representativas
  * C1: Random Forest
  * C2: CNN
    * Importação das Bibliotecas Necessárias
    * Divisão dos Conjuntos de Treinamento, Validação e Teste - CNN
    * Definição do Modelo - CNN
    * Predição e Métricas de Avaliação - CNN
    * Ajuste dos Hiperparâmetros com keras tuner - CNN
    * Predição e Métricas de Avaliação após busca de hiperparâmetros - CNN
  * C3: LSTM
    * Divisão dos Conjuntos de Treino, Validação e Teste - LSTM
    * Definição do Modelo - LSTM
    * Predição e Métricas de Avaliação - LSTM
    * Ajuste dos Hiperparâmetros com keras tuner - LSTM
    * Predição e Métricas de Avaliação após busca de hiperparâmetros - LSTM
  * C4: BERT
    * Divisão dos Conjuntos de Treino, Validação e Teste - BERT
    * Definição do Modelo - BERT
    * Predição e Métricas de Avaliação - BERT
* **Etapa 4**: Resumo das Melhores Métricas para Todos os Modelos
* **Etapa 5**: Frontend
  * Desenvolvimento do frontend no Tableau.

## Resumo das Melhores Métricas para Todos os Modelos
* Random Forest, CNN e LSTM em duas condições:
  1. Sem o uso de `stemming`;
  2. Com o uso de `stemming`.
* BERT.

### Random Forest, CNN e LSTM `Sem Stemming`

| Modelo            | Classe   | Precision | Recall | F1 Score |
|------------------:|--------: |:---------:|:------:|:--------:|
| **Random Forest** | Negativa | 0.93      | 0.05   | 0.10     |
|                   | Positiva | 0.79      | 1.00   | 0.88     |
| **CNN**           | Negativa | 0.79      | 0.66   | 0.72     |
|                   | Positiva | 0.91      | 0.95   | 0.93     |
| **LSTM**          | Negativa | 0.73      | 0.77   | 0.75     |
|                   | Positiva | 0.93      | 0.92   | 0.92     |

### Random Forest, CNN e LSTM `Com Stemming`

| Modelo            | Classe   | Precision | Recall | F1 Score |
|------------------:|--------: |:---------:|:------:|:--------:|
| **Random Forest** | Negativa | 0.53      | 0.07   | 0.12     |
|                   | Positiva | 0.78      | 0.98   | 0.87     |
| **CNN**           | Negativa | 0.81      | 0.62   | 0.70     |
|                   | Positiva | 0.90      | 0.96   | 0.93     |
| **LSTM**          | Negativa | 0.55      | 0.76   | 0.63     |
|                   | Positiva | 0.92      | 0.82   | 0.86     |

### BERT

| Modelo    | Classe   | Precision | Recall | F1 Score |
|----------:|--------: |:---------:|:------:|:--------:|
| **BERT**  | Negativa | 0.83      | 0.84   | 0.83     |
|           | Positiva | 0.95      | 0.95   | 0.95     |
