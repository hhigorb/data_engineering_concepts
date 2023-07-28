## Spark

O que é o Spark?

## Porque o Spark foi criado?

## Qual dor o Spark resolve / Objetivo do Spark?

## quais são os principais pontos do spark?

## qual a arquitetura do spark?

## o que é um cluster?


SparkContext: O SparkContext é a entrada principal para qualquer funcionalidade do Spark. É uma conexão com o cluster e é usado para criar RDDs, acumuladores e variáveis de transmissão.

SparkSession: O SparkSession é a entrada principal para funcionalidades do Spark SQL, permitindo que você execute consultas SQL e acesse recursos do DataFrame.

DataFrame e Dataset: São abstrações de dados estruturados fornecidas pelo Spark SQL. Os DataFrames são representados como tabelas com linhas e colunas, semelhantes a uma tabela SQL. Os Datasets são uma extensão dos DataFrames, fornecendo suporte a tipos de dados fortemente tipados, disponível em Java, Scala e Python.

Particionamento: Os dados em um RDD são divididos em partições, que são unidades básicas de paralelismo no Spark. O número de partições pode afetar a eficiência do processamento.

Broadcast Variables: São variáveis que podem ser compartilhadas entre todos os nós do cluster, reduzindo a necessidade de transferência de dados pela rede em operações repetidas.

Acumuladores: São variáveis que permitem que você acumule informações de todos os nós em um valor agregado no driver.

Spark UI: É uma interface web fornecida pelo Spark que permite monitorar o progresso das aplicações e o desempenho dos jobs em execução.

Modos de Execução: O Spark pode ser executado em diferentes modos, como local, modo cliente ou cluster, para fins de desenvolvimento e produção.

Partições Estreitas e Largas: No contexto de transformações, é importante entender a diferença entre transformações com partições estreitas (como map e filter) e transformações com partições largas (como groupByKey e join), pois isso afeta a eficiência do Spark.

Persistência e Cache: O Spark permite que você persista RDDs em memória ou em disco para reutilização eficiente, usando os métodos persist() e cache().

Tipos de Armazenamento: O Spark pode trabalhar com diferentes tipos de armazenamento, como HDFS, sistemas de arquivos locais ou Amazon S3.

Modo Local vs. Modo Cluster: O Spark pode ser executado localmente em uma máquina para fins de desenvolvimento e teste ou em um cluster de várias máquinas para processamento em grande escala.

Configurações e Tuning: O Spark possui várias configurações que podem ser ajustadas para otimizar o desempenho e uso eficiente de recursos, como número de partições, tamanho da memória, etc.

Integração com Ecossistema: O Spark se integra bem com várias outras ferramentas e tecnologias do ecossistema Hadoop, como HBase, Hive, Kafka, etc.
