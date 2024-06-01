# Arquitetura Kappa

Kappa Architecture é uma arquitetura de processamento de dados distribuída que visa simplificar o fluxo de processamento de dados em tempo real,
eliminando a necessidade da camada Batch Processing Layer, que vimos anteriormente no Lambda Architecture. Em vez disso, a Kappa Architecture
utiliza apenas uma camada de processamento em tempo real (Real-Time Processing Layer) e um armazenamento de logs, por exemplo:

Suponha que uma empresa de comércio eletrônico deseja monitorar e analisar o comportamento do usuário em tempo real para identificar padrões e
tendências em suas compras e usam um pipeline de dados baseado na Kappa Architecture para processar, armazenar e analisar esses dados em tempo real.

![Arquitetura Kappa](../images/arquitetura_kappa.png 'Arquitetura Kappa')

O pipeline começa com a ingestão de dados brutos, como registros de eventos do servidor da web e dados do carrinho de compras. Esses dados
são enviados para um cluster de processamento de stream em tempo real, como o Apache Kafka, onde são armazenados em um tópico de streaming.

Em seguida, os dados são processados por meio de um mecanismo de processamento de fluxo em tempo real, como o Apache Flink ou o Amazon Kinesis Data Analytics
for Apache Flink. Isso permite que a empresa analise os dados em tempo real e gere insights imediatos. Por exemplo, o sistema pode monitorar o comportamento
do usuário para identificar padrões de compra e recomendar produtos relevantes com base nesses padrões, disparando por exemplo um webhook.

Veja uma exemplo de arquitetura Kappa utilizando Apache Kafka apresentada pelo Uber, responsável por processar mais de 4 Trilhões de mensagens por dia em 2021.
Essa arquitetura passa por essas etapas de geração, tópico do Apache Kafka, processamento por várias ferramentas consumidoras, evitando a duplicação de código
que geralmente acontece no Lambda Architecute:

![Arquitetura Kappa](../images/arquitetura_kappa_uber_kafka.png 'Arquitetura Kappa')

Fonte: https://medium.com/@bernardo.costa/introdu%C3%A7%C3%A3o-%C3%A0-arquitetura-de-dados-usando-aws-6ec1947dda06
