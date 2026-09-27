# 🏦 Leitor de Extrato Bancário

Este projeto tem como objetivo **extrair e organizar as informações de um extrato bancário do Banco Inter**, transformando os dados originalmente disponíveis em um arquivo PDF em uma estrutura tabular que pode ser analisada e manipulada posteriormente no Excel.

O projeto foi desenvolvido em **Python utilizando o Google Colab**, a partir de um extrato bancário referente ao período de **29/07/2026 a 29/08/2026**. Os dados utilizados no desenvolvimento são reais e correspondem às movimentações realizadas durante esse período.

## 🔎 Etapas do projeto

### 1. Instalação e importação das bibliotecas

Inicialmente, foi instalada a biblioteca **PyPDF2**, utilizada para realizar a leitura e extração do conteúdo presente no arquivo PDF.

Em seguida, foram importadas as bibliotecas utilizadas no projeto:

* **PyPDF2** → leitura e extração do conteúdo do PDF;
* **re (Regular Expressions)** → identificação de padrões específicos no texto, como datas e valores monetários;
* **Pandas** → organização, tratamento e exportação dos dados.

### 2. Leitura do arquivo PDF

Após a importação das bibliotecas, o arquivo do extrato bancário é carregado e o número de páginas do documento é identificado.

Em seguida, é realizada a leitura de cada página do PDF. O conteúdo extraído é armazenado em uma única string, permitindo que todo o extrato seja posteriormente analisado.

### 3. Extração e organização das transações

Com o texto extraído, o conteúdo é dividido em **linhas** para facilitar sua análise.

A partir desse ponto, o código percorre cada linha do documento utilizando estruturas de repetição e **Expressões Regulares (Regex)** para identificar:

* 📅 Data da movimentação;
* 🏷️ Tipo da transação;
* 📝 Descrição da movimentação;
* 💰 Valor da transação;
* 💵 Saldo após a transação.

A data identificada no extrato é armazenada temporariamente para que possa ser associada às transações encontradas posteriormente.

As informações extraídas são armazenadas em uma lista de dados e, posteriormente, utilizadas para a criação de um **DataFrame com o Pandas**.

### 4. Tratamento dos dados

Após a criação do DataFrame, é realizado um processo de limpeza das informações extraídas.

Como o conteúdo é obtido diretamente do PDF, alguns textos adicionais presentes no documento original acabam sendo incorporados aos dados. Por isso, são aplicados padrões de remoção para eliminar informações desnecessárias, como textos relacionados ao **SAC, Ouvidoria e outros elementos do documento bancário**.

Também são removidos trechos adicionais presentes nas descrições das transações, deixando os registros mais organizados e adequados para análise.

### 5. Exportação para Excel

Após a extração e o tratamento das informações, o DataFrame final é exportado para um arquivo **Excel (`.xlsx`)**.

Dessa forma, o projeto transforma um documento originalmente estruturado em PDF em uma tabela organizada, facilitando a **visualização, manipulação e análise das movimentações bancárias**.

## 🎯 Objetivo

Além de praticar conceitos de **Python, Pandas, Expressões Regulares e manipulação de arquivos PDF**, o projeto busca demonstrar uma aplicação prática de **extração, tratamento e organização de dados (ETL)**.

O resultado final é um arquivo Excel contendo as informações das movimentações extraídas do extrato bancário, tornando os dados mais acessíveis para análises posteriores.
