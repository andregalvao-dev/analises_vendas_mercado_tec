# 📊 Análise de Vendas com Python

Projeto de análise de dados desenvolvido em Python com o objetivo de explorar informações de vendas, gerar indicadores e criar visualizações para auxiliar na tomada de decisões.

## 🚀 Objetivo do Projeto

Analisar dados de vendas de uma loja para descobrir:

* Produtos mais vendidos.
* Produtos com maior faturamento.
* Quantidade de vendas por dia.
* Faturamento total.
* Desempenho por vendedor e cidade.
* Tendências através de gráficos.

## 🛠️ Tecnologias Utilizadas

* Python
* Pandas
* Matplotlib
* CSV

## 📂 Estrutura do Projeto

```
analise-vendas/
│
├── vendas.csv              # Base de dados utilizada
│
├── analise_vendas.py       # Código principal da análise
│
├── graficos/               # Imagens dos gráficos gerados
│
└── README.md               # Documentação do projeto
```

## 📌 Etapas do Projeto

### 1. Importação dos dados

Os dados são carregados utilizando a biblioteca Pandas:

```python
import pandas as pd

dados = pd.read_csv("vendas.csv")
```

### 2. Exploração dos dados

Foram realizadas análises iniciais:

* Visualização das primeiras linhas.
* Verificação dos tipos de dados.
* Estatísticas gerais.

Exemplo:

```python
dados.head()
dados.info()
dados.describe()
```

### 3. Tratamento dos dados

A coluna de data foi convertida para o formato correto:

```python
dados["Data"] = pd.to_datetime(dados["Data"])
```

Também foi criada uma coluna de faturamento:

```python
dados["Faturamento"] = (
    dados["Quantidade"] * dados["Preco_Unitario"]
)
```

## 📈 Análises Realizadas

### Produtos mais vendidos

Agrupamento da quantidade vendida por produto:

```python
dados.groupby("Produto")["Quantidade"].sum()
```

### Faturamento por produto

Análise dos produtos que mais geraram receita:

```python
dados.groupby("Produto")["Faturamento"].sum()
```

### Vendas por dia

Análise da evolução das vendas:

```python
dados.groupby("Data")["Quantidade"].sum()
```

## 📊 Visualizações

Foram criados gráficos utilizando Matplotlib:

* Gráfico de barras para produtos mais vendidos.
* Gráfico de linhas para vendas ao longo do tempo.
* Gráfico de faturamento diário.

Exemplo:

```python
import matplotlib.pyplot as plt

vendas.plot(kind="bar")

plt.title("Vendas por Produto")
plt.show()
```

## 🎯 Principais Aprendizados

Este projeto permitiu praticar:

✅ Manipulação de dados com Pandas
✅ Leitura e análise de arquivos CSV
✅ Agrupamento de informações
✅ Criação de indicadores de negócio
✅ Visualização de dados com gráficos
✅ Organização de um projeto para portfólio no GitHub

## ▶️ Como executar o projeto

Clone o repositório:

```bash
git clone https://github.com/andregalvao-dev/analise-vendas.git
```

Instale as dependências:

```bash
pip install pandas matplotlib
```

Execute:

```bash
python analise_vendas.py
```


## 👨‍💻 Autor
André P. Galvão

Projeto desenvolvido para estudos de Análise de Dados com Python.
