# Projeto Análise Exploratória - Sammya Letícia e Petrick Gomes

## 👥 Integrantes da Dupla
- *Sammya* 
- *Petrick*

## 🔗 Base de Dados Utilizada
*Olist Brazilian E-Commerce Dataset*  
Disponível em: [Kaggle - Olist Dataset](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)

### Datasets Utilizados:
- olist_orders_dataset.csv
- olist_order_items_dataset.csv 
- olist_products_dataset.csv

## 🎯 Objetivo do Projeto
Analisar e pré-processar os dados do e-commerce brasileiro Olist para identificar fatores que influenciam a experiência e satisfação do cliente, com foco em:
- Atrasos de entrega
- Variações de preço e frete
- Categorias de produtos problemáticas
- Tempos de processamento e envio

## 📊 Descrição do Processo de Tratamento dos Dados

### 1. *Carregamento e Junção dos Dados*
- Carregamento dos 3 datasets obrigatórios
- Junção através das chaves order_id e product_id
- Dataset final unificado com 112.650 registros

### 2. *Análise Exploratória (EDA)*
- Análise da estrutura do dataset (22 colunas iniciais)
- Identificação de tipos de dados e valores ausentes
- Estatísticas descritivas das variáveis numéricas

### 3. *Limpeza de Dados*
- *Valores Ausentes*: Tratados com mediana por categoria e preenchimento estratégico
- *Duplicatas*: Nenhuma duplicata identificada
- *Inconsistências*: 8 produtos com peso zero corrigidos usando mediana da categoria
- *Outliers*: Tratados com método Z-score (capping ±3 desvios padrão)

### 4. *Conversão e Padronização*
- 6 colunas de data convertidas para datetime
- Correção de nomes de colunas (lenght → length)
- Aplicação de Normalização MinMax e Padronização Z-score

### 5. *Codificação de Dados Categóricos*
- *Label Encoding*: product_category_name (72 categorias)
- *One-Hot Encoding*: order_status (5 status)

### 6. *Feature Engineering (4 Técnicas)*
1. *Tempo de Atraso*: Entrega real vs estimada
2. *Proporção Frete/Preço*: Análise de custos relativos
3. *Densidade do Produto*: Peso/volume para análise logística
4. *Tempo de Processamento*: Eficiência interna

### 7. *Seleção de Atributos*
- Análise de correlação entre variáveis
- Identificação de atributos com baixa variância
- Filtros baseados em significância estatística

## 🚧 Principais Desafios Encontrados

### 1. *Tratamento de Valores Ausentes*
- 1.603 registros sem categoria de produto
- Datas de entrega ausentes em pedidos não concluídos
- Solução: Preenchimento com "sem_categoria" e mediana temporal

### 2. *Gestão de Outliers*
- Valores extremos em preço (até R$ 6.735)
- Frete desproporcional em alguns produtos
- Abordagem: Capping estatístico preservando a distribuição

### 3. *Feature Engineering*
- Criação de métricas temporais consistentes
- Cálculo de densidade com produtos de dimensões irregulares
- Normalização de proporções para comparação justa

### 4. *Dimensionalidade*
- 72 categorias de produtos para codificação
- Balanceamento entre informação e complexidade
- Decisão: Manter todas as categorias para análise setorial

## 📈 Principais Conclusões

### *Sobre Atrasos*
- *6.8% dos pedidos* tiveram atraso na entrega
- *Tempo de processamento* é fator chave para atrasos
- *Categorias específicas* apresentam maior incidência de problemas

### *Sobre Custos*
- *Correlação moderada* (0.329) entre preço e frete
- *Proporção média frete/preço*: 25.4%
- *Categorias identificadas* com frete desproporcional

### *Sobre Qualidade dos Dados*
- Dataset apresenta *boa qualidade geral*
- Poucos valores problemáticos após tratamento
- *Features criadas* enriquecem significativamente a análise

### *Insights para Negócio*
1. *Otimização logística* pode reduzir atrasos em 6.8% dos pedidos
2. *Revisão de fretes* em categorias específicas pode melhorar competitividade
3. *Monitoramento de tempo de processamento* é crucial para experiência do cliente

## 🛠️ Tecnologias Utilizadas
- *Python 3.x*
- *Pandas* - Manipulação de dados
- *NumPy* - Cálculos numéricos
- *Matplotlib/Seaborn* - Visualizações
- *Scikit-learn* - Pré-processamento (apenas)
- *Google Colab* - Ambiente de execução


## ▶️ Como Executar
1. Clone o repositório
2. Execute o notebook olist_analysis.ipynb
3. Os dados já estão pré-processados no arquivo CSV
   

*Desenvolvido por Sammya e Petrick*  
Última atualização: Dezembro 2025
