# Batch

Processamento em **batch** se refere a um tipo específico de processamento de dados em que os dados são coletados, processados e armazenados em grupos ou lotes, em vez de serem processados em tempo real. Isso é comumente usado para lidar com grandes volumes de dados de forma eficiente.

Exemplo:

**Coleta de Dados:** Imagine uma empresa que coleta dados de vendas de suas lojas a cada hora. Em vez de processar esses dados imediatamente à medida que eles chegam, eles podem optar por coletar todos os dados de uma hora em um único lote (batch).

**Processamento em Lotes:** Após coletar os dados de uma hora, a empresa processa esse lote de dados como um todo. Isso pode incluir cálculos, agregações, filtragens ou qualquer outra transformação necessária.

**Armazenamento:** Após o processamento, o lote de dados resultante é armazenado em um local de armazenamento, como um banco de dados ou sistema de arquivos.

**Programação:** O processamento em lotes geralmente é agendado para ocorrer em intervalos regulares, como a cada hora ou a cada dia.

Exemplo:
Suponha que uma loja online colete dados de compras dos clientes. Em vez de atualizar o estoque e gerar relatórios de vendas em tempo real, ela coleta todos os dados de compras durante o dia e processa esses dados em um lote no final do dia. Isso é um processamento em lote. O sistema pega todas as compras feitas durante o dia, realiza os cálculos necessários para atualizar o estoque e gera relatórios de vendas noturnos.

O processamento em lotes é útil quando a latência em tempo real não é crítica e permite que as empresas processem grandes volumes de dados de maneira mais eficiente, reduzindo a carga sobre os sistemas em tempo real.
