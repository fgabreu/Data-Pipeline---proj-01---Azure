# Lab-01---Azure
Projeto Interno 01 Big Data - Azure (Blueshift Brasil)

Projeto PoccoBank

Foi solicitado a criação de um processo capaz de trazer a cotação do cambio e suas variações ao longo da semana. Usando o Azure Data Factory, crie um pipeline para coletar os valores do dólar da API do Banco Central e inserir essas informações no Azure SQL, conforme desenho da arquitetura proposta. No Azure SQL crie uma Stored Procedure para converte o tipo dos dados para data e float/money/decimal e depois retornar um arquivo Parquet no Azure Storage. 




Dicionário de dados:           
    CAMPO                         TIPO                  	                             
cotacaoCompra	                    float	
cotacaoVenda	                    float	
dataHoraCotacao	                 datetime	

