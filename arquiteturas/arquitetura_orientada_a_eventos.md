# Arquitetura Orientada a Eventos

## Visão geral

A arquitetura orientada a eventos é um modelo de arquitetura de software para o design de aplicações. Em um sistema orientado a eventos, os componentes de
captura, comunicação, processamento e persistência de eventos formam a estrutura básica da solução. Isso é diferente do modelo tradicional orientado
a solicitações.

Vários designs de aplicações modernos são direcionados para eventos, como os frameworks de mecanismo do cliente, que devem utilizar dados do cliente em tempo real.
É possível criar aplicações orientadas a eventos em qualquer linguagem porque esse tipo de arquitetura é uma abordagem de programação. Com a arquitetura
orientada a eventos, você usa uma quantidade mínima de acoplamentos, o que a torna uma boa opção para arquiteturas de aplicações distribuídas modernas.

Esse tipo de arquitetura é levemente acoplado porque os produtores de eventos não sabem que os consumidores estão detectando um evento. Além disso,
esse evento não sabe as consequências da sua ocorrência.

## O que é um evento?

Um evento é qualquer ocorrência ou mudança de estado significativa no software ou hardware de um sistema. Uma notificação de evento é uma mensagem enviada
pelo sistema para avisar outra parte do mesmo sistemaque algo ocorreu. Ela não é o evento em si.

A origem de um evento pode ser interna ou externa. Os eventos podem ser gerados por um usuário que, por exemplo, clica no botão do mouse ou pressiona uma
tecla no teclado, por uma fonte externa, como uma saída de sensor, ou por um componente interno do sistema, como o carregamento de um programa.

## Como a arquitetura orientada a eventos funciona?

A arquitetura orientada a eventos é composta de produtores e consumidores de eventos. Um produtor detecta ou percebe um evento e o representa como
uma mensagem. Ele não conhece o consumidor nem o resultado do evento. 

Após um evento ser detectado, ele é transmitido do produtor para o consumidor por meio de canais, em que uma plataforma processa eventos de maneira
assíncrona. O consumidor precisa ser informado quando um evento ocorre. Ele pode processar ou apenas ser afetado pelo evento. 

A plataforma de processamento de eventos executa a resposta correta para um determinado evento e envia a atividade em sentido downstream, para os
consumidores certos. É nessa atividade downstream que o resultado do evento é visto. 

O Apache Kafka é uma plataforma de transmissão de dados distribuída muito usada para o processamento de eventos. Ele é capaz de realizar publicações,
subscrições, armazenamento e processamento de fluxos de eventos em tempo real. O Apache Kafka é compatível com vários casos de uso em que alta taxa
de transferência e escalabilidade são essenciais. Além disso, por minimizar a necessidade de integrações point-to-point (P2P) para o compartilhamento
de dados em determinadas aplicações, essa plataforma ajuda a reduzir a latência a milésimos de segundos. 

Há outros gerenciadores de eventos de middleware disponíveis que podem servir de plataforma de processamento de eventos.

## Modelos de arquitetura orientada a eventos

A arquitetura orientada a eventos pode ser baseada em um modelo de publicação/subscrição (pub/sub) ou de transmissão de eventos.

### Modelo de pub/sub

Trata-se de uma infraestrutura de mensageria baseada em subscrições em um fluxo de eventos. Nesse modelo, após um evento ocorrer
ou ser publicado, ele é enviado aos subscritores que precisam ser informados.

### Modelo de transmissão de eventos

No modelo de transmissão, os eventos são gravados em um log. Os consumidores não precisam se inscrever em uma transmissão de evento.
Na verdade, eles podem ler a partir de qualquer parte da transmissão e ingressar nela a qualquer momento. 

Há alguns tipos de transmissão de eventos:

#### Processamento do fluxo do evento: 
  - Usa uma plataforma de transmissão, como o Apache Kafka, para ingerir e processar eventos ou transformar seu fluxo. Esse método pode ser usado para detectar padrões significativos em fluxos de eventos.
    
#### Processamento de evento simples:
  - é quando um evento aciona imediatamente uma ação no consumidor.
    
#### Processamento de evento complexo: 
  - requer que um consumidor processe uma série de eventos para detectar padrões.

## Benefícios da arquitetura orientada a eventos

Ao adotar uma arquitetura orientada a eventos, as organizações conquistam um sistema flexível capaz de se adaptar a mudanças e tomar
decisões em tempo real. Ser capaz de reconhecer situações em tempo real significa que a tomada de decisões de negócios, seja esse
processo manual ou automatizado, é feita usando todos os dados disponíveis que reflitam o estado atual dos sistemas. 

À medida que ocorrem, os eventos são capturados em origens como redes, aplicações e dispositivos de Internet das Coisas (IoT).
Isso permite que produtores e consumidores de eventos compartilhem informações sobre status e resposta em tempo real. 

As organizações podem agregar a arquitetura orientada a eventos aos seus sistemas e aplicações para aprimorar a escalabilidade e a
capacidade de resposta, além de acessar os dados e o contexto necessários para um processo de tomada de decisões empresariais mais eficiente.
