# Arquitetura Lambda

## Os desafios do Big Data

Os sistemas de dados são mais úteis quando respondem corretamente às perguntas certas sobre todos os dados que contêm. Com o big data, no entanto, novos
dados entram no sistema a cada minuto — e são muitos. O sistema de dados enfrenta dois desafios fundamentais.

### Desafio nº 1: O problema da latência. Posso obter respostas super precisas às suas perguntas com base em todos os dados transmitidos desde o início da minha existência até este exato momento, mas isso vai demorar um pouco. Espero que não se importe em esperar.

### Desafio 2: O problema de precisão. Finalmente consegui minhas respostas super precisas para você. Infelizmente, eles levaram muito tempo para adquiri-los, eles não estão mais atualizados e precisos.

Arquitetura Lambda é um paradigma de big data, uma forma de estruturar um sistema de dados para superar o problema de latência e o problema de precisão.
Foi introduzido pela primeira vez por Nathan Marz e James Warren em 2015. A Arquitetura Lambda estrutura o sistema em **três camadas:** uma camada de lote (**batch layer**),
uma camada rápida (**speed layer**) e uma camada de serviço (**serving layer**).

![Arquitetura Lambda](../images/arquitetura_lambda.png 'Arquitetura Lambda')

## Batch Layer 

Como mencionado acima, a arquitetura Lambda é composta de três camadas. A primeira camada — a camada de lote — armazena todo o conjunto de dados e calcula
visualizações em lote. O conjunto de dados armazenado é imutável e somente anexado. Novos dados são continuamente transmitidos e anexados ao conjunto de dados,
mas os dados antigos sempre permanecerão inalterados. A camada de lote também calcula visualizações em lote, que são consultas ou funções em todo o conjunto
de dados. Essas visualizações podem ser subsequentemente consultadas para respostas de baixa latência a perguntas de todo o conjunto de dados. A desvantagem,
no entanto, é que leva muito tempo para calcular essas visualizações em lote.

## Serving Layer 

É a camada responsável por indexar os dados processados nas camadas anteriores, permitindo que queries ad-hoc sejam feitas.

A segunda camada na arquitetura Lambda é a camada de serviço. A camada de serviço é carregada nas visualizações em lote e, como um banco de dados tradicional,
permite consultas somente leitura nessas visualizações em lote, fornecendo respostas de baixa latência. Assim que a camada de lote tiver um novo conjunto de
visualizações de lote pronto, a camada de serviço troca o conjunto agora obsoleto de visualizações de lote pelo conjunto atual.

## Speed Layer

A terceira camada é a camada de velocidade. Os dados que são transmitidos para a camada de lote também são transmitidos para a camada de velocidade.
A diferença é que, embora a camada de lote mantenha todos os dados desde o início de seu tempo, a camada de velocidade só se preocupa com os dados
que chegaram desde o último conjunto de visualizações de lote concluído. A camada de velocidade compensa a alta latência na computação de exibições
em lote, processando consultas nos dados mais recentes que as exibições em lote ainda precisam levar em consideração.

Este modelo é proposto seguindo as seguintes premissas:

  - Robustez e tolerância a falhas;
  - Baixa latência para leitura e atualização;
  - Escalabilidade;
  - Generalização;
  - Extensibilidade;
  - Ad hoc queries;
  - Manutenção mínima;
  - Fácil de debugar;

## Porque utilizar a arquitetura Lambda?

### Vantagens
![Arquitetura Lambda](../images/vantagens_arquitetura_lambda.png 'Arquitetura Lambda')

No livro seminal de Marz e Warren sobre Big Data de Arquitetura Lambda, eles listam oito propriedades desejáveis ​​em um sistema de Big Data,
descrevendo como a Arquitetura Lambda satisfaz cada uma delas:

Robustez e tolerância a falhas. Como a camada de lote é projetada para ser apenas anexada, contendo todo o conjunto de dados desde o início dos tempos,
o sistema é tolerante a falhas humanas. Se houver corrupção de dados, todos os dados do ponto de corrupção em diante podem ser excluídos e substituídos
pelos dados corretos. As visualizações em lote podem ser trocadas por outras completamente recalculadas. A camada de velocidade pode ser descartada.
No tempo que leva para gerar um novo conjunto de visualizações em lote, todo o sistema pode ser reiniciado e executado novamente.

### Escalabilidade
  - A arquitetura Lambda é projetada com camadas construídas como sistemas distribuídos. Simplesmente adicionando mais máquinas, os usuários finais
podem facilmente escalar horizontalmente esses sistemas.

### Generalização
  - Uma vez que a arquitetura Lambda é um paradigma geral, os adotantes não estão presos a uma forma específica de calcular esta ou aquela visualização
em lote. As visualizações em lote e os cálculos da camada de velocidade podem ser projetados para atender às necessidades específicas do sistema de dados.

### Extensibilidade
  - À medida que novos tipos de dados entram no sistema de dados, novas visualizações se tornam necessárias. Os sistemas de dados não estão bloqueados
em certos tipos ou um certo número de visualizações em lote. Novas visualizações podem ser codificadas e adicionadas ao sistema, com a única
restrição sendo os recursos, que são facilmente escaláveis.

### Consultas ad hoc 
  - Se necessário, a camada de lote pode suportar consultas ad hoc que não estavam disponíveis nas visualizações de lote. Supondo que a alta latência para essas
consultas ad hoc seja permitida, a utilidade da camada de lote não se restringe apenas às visualizações de lote que ela gera.

### Manutenção mínima
  - A Arquitetura Lambda , em sua encarnação típica, usa Apache Hadoop para a camada de lote e ElephantDB para a camada de serviço. Ambos são bastante simples de manter.

### Depurabilidade
  - As entradas para o cálculo das visualizações em lote da camada de lote são sempre as mesmas: todo o conjunto de dados. Em contraste com as
visualizações de depuração computadas em um instantâneo de um fluxo de dados, as entradas e saídas para cada camada na Arquitetura Lambda não são
alvos móveis, simplificando enormemente a depuração de cálculos e consultas.

### Leituras e atualizações de baixa latência
- Na arquitetura Lambda, a última propriedade de um sistema de big data é preenchida pela camada de velocidade, que oferece consultas em tempo real do conjunto de dados mais recente.

## Desvantagens da arquitetura Lambda

### Desvantagens
![Arquitetura Lambda](../images/desvantagens_arquitetura_lambda.png 'Arquitetura Lambda')

Embora as vantagens da arquitetura Lambda pareçam numerosas e diretas, há algumas desvantagens a serem lembradas. Em primeiro lugar, o custo será levado em
consideração. Embora como dimensionar não seja muito complexo — basta adicionar mais máquinas — podemos ver que a camada de lote precisará necessariamente
se expandir e crescer com o tempo. Como todos os dados são apenas anexados e nenhum dado na camada de lote é descartado, o custo de escalonamento
necessariamente aumentará com o tempo.

Outros notaram o desafio de manter dois conjuntos separados de código para computar visualizações para a camada de lote e a camada de velocidade. Ambas
as camadas operam no mesmo conjunto — ou, no caso da camada de velocidade, subconjunto — de dados, e as perguntas feitas a ambas as camadas são semelhantes.
No entanto, como as duas camadas são construídas em sistemas completamente diferentes (por exemplo, Hadoop ou Snowflake para a camada de lote, mas Storm ou
Spark para a camada de velocidade), a manutenção de código para dois sistemas separados pode ser complicada.

Fonte: https://uderson.medium.com/uma-vis%C3%A3o-geral-da-arquitetura-lambda-50c9e059a0b0
