# Projeto de Análise de Dados com Python

Este projeto serve para organizar, limpar e analisar dados. Ele usa Python com Pandas para tratar as tabelas, SQL para puxar as informações do banco e a biblioteca Rich para deixar as respostas no terminal mais fáceis de ler.

## Como o projeto está organizado

* data/: Pasta onde entram os arquivos originais (CSV, JSON) e onde salvamos os dados já limpos.
* src/: Scripts em Python que fazem a limpeza e a transformação dos dados.
* queries/: Arquivos com as consultas em SQL usadas para buscar as informações.
* main.py: Arquivo principal que roda todo o processo.

## O que você precisa ter instalado

* Python 3.10 ou mais recente
* Acesso a um banco de dados SQL
* O instalador pip

## Bibliotecas usadas

* pandas
* rich
* sqlalchemy
* psycopg2-binary

Para instalar todas de uma vez, rode no terminal:

pip install -r requirements.txt

### Passo a passo para rodar

1. Baixe o projeto para a sua máquina:
   git clone <URL_DO_REPOSITORIO>

2. Entre na pasta do projeto:
   cd <NOME_DO_DIRETORIO>

3. Configure o acesso ao banco de dados:
   Crie um arquivo com o nome `.env` na pasta principal do projeto e coloque os dados de conexão do seu banco, desse jeito:
   DB_HOST=localhost
   DB_PORT=5432
   DB_NAME=nome_do_banco
   DB_USER=usuario
   DB_PASS=senha

4. Rode o programa:
   python main.py
