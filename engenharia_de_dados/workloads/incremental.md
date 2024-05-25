# Processamento Incremental

O processamento "incremental" refere-se a uma abordagem ou processo que envolve atualizar, adicionar ou modificar dados de maneira incremental,
em vez de realizar operações de processamento em lotes de dados completos. Essa abordagem é frequentemente usada para lidar com grandes
volumes de dados que estão em constante evolução, como registros de logs, dados de streaming, atualizações de bancos de dados em tempo
real, entre outros.

A principal ideia por trás do processamento incremental é a seguinte:

#### Atualização contínua: 
 - Em vez de reprocessar todos os dados sempre que uma alteração ou adição ocorre, apenas os dados afetados são processados.

#### Eficiência: 
  - O processamento incremental é mais eficiente em termos de recursos computacionais e tempo, pois não é necessário reprocessar grandes conjuntos de dados inteiros repetidamente.

#### Baixa latência: 
  - O processamento incremental permite que as mudanças nos dados sejam refletidas em tempo real ou em intervalos curtos, proporcionando baixa latência para os sistemas que dependem desses dados.

Há várias técnicas e ferramentas disponíveis para implementar o processamento incremental em engenharia de dados, incluindo:

#### CDC (Change Data Capture): 
  - Uma técnica que identifica e captura as mudanças ocorridas nos dados em tempo real ou em intervalos regulares.

#### Streaming: 
  - Processamento de dados em tempo real por meio de sistemas de streaming, como Apache Kafka ou Apache Flink, que permitem a análise contínua de dados à medida que eles chegam.

#### SCD (Slowly Changing Dimension): 
  - Um conceito em data warehousing que lida com a atualização incremental de dimensões em um armazém de dados.

#### Banco de dados NoSQL: 
  - Bancos de dados NoSQL, como Cassandra e MongoDB, são frequentemente usados para armazenar e consultar dados em tempo real, permitindo atualizações incrementais.

O processamento incremental é crucial em muitos cenários de negócios e aplicativos, onde a capacidade de responder rapidamente a mudanças nos dados é fundamental, como em análises em tempo real, detecção de fraudes, recomendações personalizadas, entre outros.

A escolha entre o processamento "full" e o processamento "incremental" depende dos requisitos do seu caso de uso específico.
O processamento incremental é mais apropriado quando a latência é crítica e você precisa responder rapidamente a mudanças nos dados. 
O processamento "full" é mais apropriado quando a consistência e a integridade dos dados são prioritárias e você pode se dar ao
luxo de lidar com atualizações periódicas em lotes.
