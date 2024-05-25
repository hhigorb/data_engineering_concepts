# Processamento Full

O processamento "full" em engenharia de dados é uma abordagem que envolve o processamento de todos os dados de uma vez, 
em vez de tratar os dados de forma incremental. Isso significa que, ao realizar uma operação de processamento "full", 
você processa e analisa um conjunto completo de dados, em vez de lidar com atualizações ou adições incrementais.

Alguns pontos importantes sobre o processamento "full" incluem:

#### Requisitos de recursos: 
  - O processamento "full" geralmente requer mais recursos computacionais, tempo e capacidade de
armazenamento do que o processamento incremental, especialmente quando se lida com grandes volumes de dados.

#### Atualização periódica: 
  - Em vez de atualizar os dados à medida que mudanças ocorrem, o processamento "full" geralmente envolve atualizações periódicas em lotes, em intervalos definidos.

#### Consistência: 
  - Como todos os dados são processados de uma só vez, a operação de processamento "full" garante maior consistência entre os dados, pois eles são tratados como um conjunto completo.

O processamento "full" é frequentemente usado em cenários em que a consistência e a integridade dos dados são fundamentais,
e a latência não é um fator crítico. Por exemplo, em processos de ETL (Extração, Transformação e Carga) em data warehousing,
é comum realizar operações "full" para criar data marts ou atualizar relatórios em intervalos diários, semanais ou mensais.

A escolha entre o processamento "full" e o processamento "incremental" depende dos requisitos do seu caso de uso específico.
O processamento incremental é mais apropriado quando a latência é crítica e você precisa responder rapidamente a mudanças nos dados. 
O processamento "full" é mais apropriado quando a consistência e a integridade dos dados são prioritárias e você pode se dar ao
luxo de lidar com atualizações periódicas em lotes.
