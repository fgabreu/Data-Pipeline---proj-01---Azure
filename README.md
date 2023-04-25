# Proj-01---Azure
Projeto 01 Big Data - Azure 

Foi solicitado a criação de um processo capaz de trazer a cotação do cambio e suas variações ao longo da semana. Usando o Azure Data Factory, crie um pipeline para coletar os valores do dólar da API do Banco Central e inserir essas informações no Azure SQL, conforme desenho da arquitetura proposta. 
No Azure SQL crie uma Stored Procedure para converte o tipo dos dados para data e float/money/decimal e depois retornar um arquivo Parquet no Azure Storage. 

Arquitetura Proposta:

![ARQUITETURA](https://user-images.githubusercontent.com/57818977/220187836-817ab9fb-d9d1-4196-bbec-ddb59168d096.png)

O link API do Banco Central com os valores do dólar: https://olinda.bcb.gov.br/olinda/servico/PTAX/versao/v1/odata/CotacaoDolarPeriodo(dataInicial=@dataInicial,dataFinalCotacao=@dataFinalCotacao)?@dataInicial='01-01-2019'&@dataFinalCotacao='12-31-2025'&$top=9000&$format=text/csv&$select=cotacaoCompra,cotacaoVenda,dataHoraCotacao

O arquivo contendo os valores está no formato CSV.

Estruturação do Projeto:

![DICIONARIO DE DADOS](https://user-images.githubusercontent.com/57818977/220189519-f1a5b7e0-cecf-434f-8a40-1ae7a25d77b7.png)


To Do:

Azure SQL
Schemas:
- Criar uma tabela stage chamada schema.dolar_Stage_seu_nome com o tipo de dado Varchar
- Criar uma tabela final para receber os dados convertidos schema.dolar_final_seu_nome
- CRIAR uma procedure (qualquer nome) dentro do seu schema para popular a tabela final com os dados convertidos.


Data Factory:
- Copiar os dados vindo do banco central e popular a tabela stage;
- Criar uma atividade de procedure para executar a procedure de conversão do Azure SQL;
- Criar uma atividade de copiar buscando os dados da tabela final com dados convertidos e salvar como PARQUET no blob.
- Dica de source: HTTP.


RESULTADO FINAL PIPELINE AZURE DATAFACTORY:

![Pipeline](https://user-images.githubusercontent.com/57818977/220189104-15b630e4-95c4-4e15-95ac-5ca1a3410982.png)
