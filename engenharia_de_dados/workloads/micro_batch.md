# Micro Batch

O **micro batch** é uma abordagem intermediária entre o processamento em lote (batch processing) e o processamento em tempo real (streaming). Nessa abordagem, os dados são processados em pequenos lotes ou mini lotes em intervalos regulares, em vez de processá-los individualmente em tempo real ou em grandes volumes em lotes.

**Processamento em Lote vs. Workload Streaming vs. Micro Batch:**

**Processamento em Lote:**
  - O processamento em lote envolve o processamento de grandes volumes de dados em intervalos programados.
    
**Workload Streaming:**
  - No workload streaming, os dados são processados à medida que são gerados ou coletados, em tempo real.
    
**Micro Batch:**
  - No micro batch, os dados são agrupados em pequenos lotes e processados em intervalos regulares. Isso permite um equilíbrio entre o processamento em lote e o streaming, tornando-o adequado para casos em que a latência em tempo real não é crítica, mas ainda se deseja um processamento mais rápido do que o processamento em lote tradicional.
    
**Exemplo de Caso de Uso:**
Suponha que uma empresa de análise de vendas deseja calcular as estatísticas de vendas diárias com base em transações de vendas que ocorrem em uma loja de varejo. Em vez de processar cada transação individualmente em tempo real (workload streaming) ou esperar até o final do dia para processar todas as transações (processamento em lote), a empresa pode usar o micro batch. Nesse caso, as transações seriam agrupadas em pequenos lotes, como a cada 15 minutos, e, em seguida, esses lotes seriam processados para calcular as estatísticas diárias. Isso permite que a empresa tenha uma visão quase em tempo real das vendas diárias, mas sem a sobrecarga de processamento de cada transação instantaneamente.

O micro batch é frequentemente usado quando a latência em tempo real não é crítica, mas ainda é importante processar dados em intervalos mais curtos do que o processamento em lote tradicional. Ele oferece um compromisso entre o processamento em tempo real e o processamento em lote, tornando-o adequado para muitos casos de uso de engenharia de dados, como análise de dados de IoT, processamento de logs de servidor e agregação de dados para relatórios periódicos.
