# Spark

## O que é o Spark?

- O Spark é uma ferramenta para processamento de grandes volumes de dados, proporcionando análise rápida e eficiente. Ele suporta várias tarefas, como processamento em lote, consultas SQL, streaming, aprendizado de máquina e processamento de gráficos, sendo capaz de trabalhar com qualquer quantidade de dados de forma escalável e eficiente.

É distribuído em alguns módulos: 

- **Spark SQL**
  - É usado para manipular dados estruturados e semiestruturados usando consultas SQL e pode ler de várias fontes de dados.
  
- **Spark Streaming**
  - Este módulo processa dados em tempo real de diferentes fontes, incluindo Kafka, Flume, Kinesis e TCP sockets.
  
- **Spark Machine Learning**
  - É uma biblioteca para aprendizado de máquina, fornecendo uma variedade de algoritmos para análise preditiva, classificação, detecção de anomalias e muito mais.
  
- **Spark Graph (GraphX)**
  - É uma biblioteca para manipular e calcular gráficos de maneira paralela. É útil para análise de redes sociais, sistemas de recomendação e análise de redes de internet.

## Porque o Spark foi criado?

O Spark foi criado para superar limitações do MapReduce do Hadoop, principalmente sua ineficiência em algoritmos que requerem várias iterações. O Spark acelera esses processos armazenando resultados intermediários na memória do sistema, ao invés de ler e gravar no disco a cada passo. Além disso, foi projetado para ser mais fácil de usar, com APIs de alto nível e suporte para SQL e ferramentas de ciência de dados, facilitando o desenvolvimento de aplicativos de processamento de dados complexos.

## Processamento em Memória do Spark

O Spark usa a memória do sistema (RAM) para armazenar dados intermediários por duas razões principais: velocidade e eficiência.

O acesso à memória RAM é muito mais rápido do que o acesso ao disco rígido (HD). Ao armazenar dados na memória, o Spark pode acessá-los e processá-los muito mais rapidamente, o que resulta em uma execução mais rápida das tarefas. Isto é particularmente útil para algoritmos que precisam de várias passagens pelos mesmos dados, como muitos algoritmos de aprendizado de máquina e análise de dados.

Além disso, ao manter os dados na memória, o Spark evita a sobrecarga de E/S (entrada/saída) associada à leitura e gravação constantes de dados no disco, o que pode ser um gargalo significativo em termos de desempenho em sistemas de processamento de dados distribuídos. Isto torna o Spark mais eficiente na execução de tarefas de processamento de dados.

No entanto, é importante notar que o Spark não usa exclusivamente a memória. Ele também tem a capacidade de armazenar dados no disco se a memória do sistema estiver cheia, embora isso possa diminuir a velocidade do processamento. Esta é uma característica de "tolerância a falhas", que permite ao Spark continuar a processar mesmo se a quantidade de dados exceder a quantidade de memória disponível.

## Qual a arquitetura do spark?

A arquitetura do Spark é baseada em um conceito chamado "computação distribuída". Isso significa que ele divide os dados e as tarefas computacionais em várias partes e as distribui entre muitas máquinas em um cluster para processamento. Aqui estão os principais componentes dessa arquitetura:

- **Driver Program**
  - Este é o programa principal, a aplicação que você escreve e executa. O Driver Program contém o código que define as transformações e ações sobre os dados e cria um SparkContext.

- **SparkContext**
  - Este é o coração de qualquer aplicação Spark. Ele estabelece a conexão com o cluster de computação e coordena e monitora a execução de tarefas. O SparkContext distribui as tarefas (funções) ao Executor nos Worker Nodes.

- **Cluster Manager**
  - É o responsável por gerenciar e alocar recursos no cluster. Ele recebe do SparkContext as solicitações de recursos para execução de tarefas. O Spark suporta vários gerenciadores de cluster, incluindo standalone (gerenciamento integrado do Spark), Hadoop YARN e Apache Mesos.

- **Worker Node**
  - Estes são os nós onde as tarefas realmente são executadas. Cada Worker Node tem Executors, que são processos que executam as tarefas. Eles também armazenam e cacheiam todos os dados particionados para suas tarefas.

Em resumo, o Driver Program, através do SparkContext, divide o programa em tarefas e as envia para o Executor nos Worker Nodes via Cluster Manager. Cada Executor executa as tarefas e retorna os resultados ao SparkContext. Isso permite ao Spark processar grandes quantidades de dados muito mais rapidamente do que seria possível em uma única máquina.

## O que é um Cluster?

Um cluster, no contexto da computação, é um conjunto de computadores conectados que trabalham juntos como se fossem um único sistema. Cada computador individual dentro de um cluster é conhecido como um nó.

Esses nós de computação podem ser máquinas físicas separadas ou podem ser instâncias virtuais em um ambiente de nuvem. Eles são conectados por uma rede de alta velocidade, o que permite que os dados sejam trocados rapidamente entre os nós.

Os clusters são usados em computação distribuída, onde tarefas são divididas em muitas sub-tarefas menores que são distribuídas entre os nós do cluster. Isso permite que grandes quantidades de dados sejam processadas mais rapidamente do que seria possível em uma única máquina, porque as tarefas são realizadas em paralelo.

No contexto do Spark, um cluster se refere ao conjunto de máquinas que o Spark pode usar para executar tarefas. O Spark divide os dados e as tarefas computacionais entre os nós do cluster, e os resultados de cada tarefa são então combinados para produzir a saída final.

## Conceitos Extras

- **SparkContext**
  - O SparkContext é a entrada principal para qualquer funcionalidade do Spark. É uma conexão com o cluster e é usado para criar RDDs, acumuladores e variáveis de transmissão.

- **SparkSession**
  - O SparkSession é a entrada principal para funcionalidades do Spark SQL, permitindo que você execute consultas SQL e acesse recursos do DataFrame.

- **DataFrame e Dataset**
  - São abstrações de dados estruturados fornecidas pelo Spark SQL. Os DataFrames são representados como tabelas com linhas e colunas, semelhantes a uma tabela SQL. Os Datasets são uma extensão dos DataFrames, fornecendo suporte a tipos de dados fortemente tipados, disponível em Java, Scala e Python.

- **Particionamento**
  - Os dados em um RDD são divididos em partições, que são unidades básicas de paralelismo no Spark. O número de partições pode afetar a eficiência do processamento.

- **Broadcast Variables**
  - São variáveis que podem ser compartilhadas entre todos os nós do cluster, reduzindo a necessidade de transferência de dados pela rede em operações repetidas.

- **Acumuladores**
  - São variáveis que permitem que você acumule informações de todos os nós em um valor agregado no driver.

- **Spark UI**
  - É uma interface web fornecida pelo Spark que permite monitorar o progresso das aplicações e o desempenho dos jobs em execução.

- **Modos de Execução**
  - O Spark pode ser executado em diferentes modos, como local, modo cliente ou cluster, para fins de desenvolvimento e produção.

- **Partições Estreitas e Largas**
  - No contexto de transformações, é importante entender a diferença entre transformações com partições estreitas (como map e filter) e transformações com partições largas (como groupByKey e join), pois isso afeta a eficiência do Spark.

- **Persistência e Cache**
  - O Spark permite que você persista RDDs em memória ou em disco para reutilização eficiente, usando os métodos persist() e cache().

- **Tipos de Armazenamento**
  - O Spark pode trabalhar com diferentes tipos de armazenamento, como HDFS, sistemas de arquivos locais ou Amazon S3.

- **Modo Local vs. Modo Cluster**
  -  O Spark pode ser executado localmente em uma máquina para fins de desenvolvimento e teste ou em um cluster de várias máquinas para processamento em grande escala.

- **Configurações e Tuning**
  - O Spark possui várias configurações que podem ser ajustadas para otimizar o desempenho e uso eficiente de recursos, como número de partições, tamanho da memória, etc.

- **Integração com Ecossistema**
  - O Spark se integra bem com várias outras ferramentas e tecnologias do ecossistema Hadoop, como HBase, Hive, Kafka, etc.
