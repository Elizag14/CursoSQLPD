# CursoSQLPD
Curso Aberto de SQL para Análise de Dados do canal Programação Dinâmica.
O dataset utilizado nesse projeto é público, o que significa que foi disponibilizado pelo TSE e pode ser acessado por qualquer pessoa interessada em estudar e analisar dados.
Essa acessibilidade pública oferece uma grande vantagem, pois permite que pesquisadores, cientistas e entusiastas da área de utilizem esses dados em suas análises e estudos.
No nosso caso, estamos utilizando o BigQuery, uma plataforma poderosa de processamento e análise de dados fornecida pelo Google Cloud Platform (GCP).
Quem precisa aprender SQL e quer um ambiente com dados reais para treinar sem a necessidade de instalar nenhum programa é uma ótima ferramenta.
O BigQuery é um data warehouse corporativo sem servidor e econômico que funciona em nuvens e pode ser escalonado de acordo com seus dados. 
O Google permite que um novo usuário armazene até 10 GB de dados e consulte até 1 TB de dados por mês gratuitamente.
O Canal programação dinâmica possui uma playlist completa chamado curso Aberto de SQL para Análise de Dados.

https://www.youtube.com/watch?v=BRPUA0EgS4I&list=PL5TJqBvpXQv5n1N15kcK1m9oKJm_cv-m6

Esse curso se destina a quem deseja aprender a extrair informações de bancos de dados utilizando SQL. Utilizaremos como ambiente de aprendizado o Big Query e como fontes de dados, algumas entre as inúmeras bases de dados disponibilizadas, tratadas e mantidas pelo projeto Base dos Dados.

//ver todas colunas da tabela
SELECT * FROM `basedosdados.br_poder360_pesquisas.microdados` LIMIT 1000

// selecionar,as colunas: ano,cargo, sigla do partido
SELECT ano,cargo, sigla_partido FROM `basedosdados.br_poder360_pesquisas.microdados` LIMIT 1000

//filtrando o municipio Duque de Caxias
SELECT * FROM `basedosdados.br_poder360_pesquisas.microdados` 
WHERE nome_municipio = "Duque de Caxias"
LIMIT 10;

//selecionando todos os institutos sem repetir//
SELECT DISTINCT instituto
FROM `basedosdados.br_poder360_pesquisas.microdados`

//pesquisar instituto DataFolha após 2013
SELECT * FROM `basedosdados.br_poder360_pesquisas.microdados`
WHERE instituto = 'Datafolha' AND ano >2013;


//pesquisar instituto DataFolha e Ibope
SELECT * FROM `basedosdados.br_poder360_pesquisas.microdados`
WHERE instituto = 'Datafolha' OR instituto= 'Ibope'
LIMIT 1000;

//pesquisar instituto DataFolha e Ibope no ano 2018
SELECT * FROM `basedosdados.br_poder360_pesquisas.microdados`
WHERE (instituto = 'Datafolha' OR instituto= 'Ibope') and ano =2018
LIMIT 1000;

//pesquisar instituto DataFolha e Ibope no ano 2018 e em SP
SELECT * FROM `basedosdados.br_poder360_pesquisas.microdados`
WHERE (instituto = 'Datafolha' OR instituto= 'Ibope') and ano =2018 and sigla_uf = 'SP'
LIMIT 1000;

//pesquisar instituto DataFolha e Ibope no ano 2018 e em SP
SELECT * FROM `basedosdados.br_poder360_pesquisas.microdados`
WHERE (instituto = 'Ibope') and ano =2018 and sigla_uf = 'SP'
LIMIT 1000;

//pesquisar quais institutos que tem em SP no ano 2018 
SELECT DISTINCT instituto from `basedosdados.br_poder360_pesquisas.microdados`
where ano =2018 and sigla_uf = 'SP'


//quais as siglas dos partidos, que apareceram em pesquisas eleitoras de 2014 até agora.
SELECT DISTINCT sigla_partido FROM `basedosdados.br_poder360_pesquisas.microdados`
where ano >2014

