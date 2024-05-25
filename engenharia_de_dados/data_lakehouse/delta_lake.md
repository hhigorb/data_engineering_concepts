# Delta Lake

# O que é o Delta Lake?

Criado pelo time da Databricks, Delta Lake é um projeto opensource para armazenamento de arquivos, baseado no formato delta, persistidos no HDFS ou em Data Lakes (AWS, Azure, GCP), utilizando
o Spark como motor de transformação e persistência. Esse formato trará algumas vantagens que veremos a seguir no artigo, como transações ACID e versionamento dos dados. 

# Como funciona o armazenamento no Delta Lake?

Embora à primeira vista o “delta” se pareça um novo formato de armazenamento, de fato, ele nada mais é do que uma mescla de armazenamento físico em Parquet (compressão Snappy) - que é um formato
colunar muito utilizado no mundo dos dados – junto à uma camada adicional de metadados/logs transacionais. Aqui cabem duas observações importantes: 

1. Os metadados/logs são persistidos no mesmo diretório da tabela Delta que está sendo manipulada, portanto não é necessário nenhuma infraestrutura adicional para armazenar esses arquivos.
Abaixo vemos um exemplo da estrutura do diretório de uma tabela chamada my_table, particionada pelo campo date.

2. Essa camada de logs (_delta_log) irá registrar todas as alterações realizadas na tabela, salvando o histórico de transformações em arquivos json/parquet e mantendo sempre a versão
mais recente das alterações como padrão, porém permitindo acessar versões anteriores da tabela também.Com base nesses arquivos que o Delta nos permite viajar no tempo, pois
nos permite acessar versões antigas da tabela para consultar ou até restaurar a tabela inteira para uma versão anterior.

# Quais as vantagens do Delta Lake?

- Transações ACID (atomicidade, consistência, isolamento e durabilidade) para as tabelas
- Escalabilidade: por se utilizar de Data Lakes nativos da Cloud, ela permite escalabilidade de petabytes
- Viagem no tempo e auditoria dos registros: possível ver versões antigas da tabela e também os registros da sessão que  a modificou
- Reforço e evolução dos schemas da tabela
- Suporte à operações de Updates, Merges e Deletes
- Funciona tanto para jobs batch quanto para streaming
- Estratégia eficaz para múltiplas leituras e escritas concorrentes nas tabelas Delta 
- APIs de fácil acesso, podendo ser utilizado em Python, SQL ou Scala por meio do Spark
- Permite remover arquivos antigos com o comando VACUUM

# Utilização do Delta Lake

A utilização do formato delta é bem simples e está disponível por meio das APIs do Spark em Python (Pyspark), SQL e Scala. Abaixo alguns exemplos simples de como é possível utilizar o formato com SQL:

![Delta Lake](../../images/delta_lake1.png 'Delta Lake')

---

![Delta Lake](../../images/delta_lake2.png 'Delta Lake')

Também são permitidas operações DML no Delta Lake. São permitidos comandos como INSERT, UPDATE, MERGE e DELETE. Conforme visto, a tecnologia do Delta Lake e seu formato delta trazem
inúmeros benefícios para os times de dados que já fazem utilização do Spark ou que gostariam de começar a utilizá-lo. Embora tenha sido desenvolvido pelo Databricks, o Delta Lake
é open source e pode ser utilizado em diversos outros tipos de aplicações Spark como o EMR (AWS), Dataproc (Google Cloud), Kubernetes e On-premises.  A possibilidade de ter
tabelas ACID em seu Delta Lake permitiu a criação de um novo conceito no mundo de dados, o Data Lakehouse, que se propõe a ser a fusão do Data Lake com o tradicional Data Warehouse.

Fonte: https://roxpartner.com/conheca-o-delta-lake/
