# Arquivo Delta

O formato delta é uma abordagem para armazenar e gerenciar dados que oferece vantagens significativas em termos de desempenho e eficiência na atualização e consulta de dados.

Baseado no parquet, arquivo estruturado orientado por colunas, é um formato desenvolvido pela Databricks para utilização no Delta Lake. De certa forma podemos pensar
num parquet com metadados, armazenando logs bem como checkpoints dos arquivos.

## Alguns pontos importantes sobre esse formato de arquivo:

### Armazenamento de Dados Incremental: 
- O formato delta é projetado para armazenar dados incrementais, ou seja, ele registra apenas as alterações nos dados em relação
à versão anterior. Isso torna o armazenamento e a atualização de dados mais eficientes.

### Histórico de Versões: 
- O formato delta mantém um histórico das versões anteriores dos dados, permitindo que os usuários acessem e consultem dados em qualquer
ponto no tempo. Isso é valioso para análises retrospectivas e auditorias.

### Transações ACID: 
 - Muitas implementações do formato delta são construídas para serem transacionais e seguem as propriedades ACID (Atomicidade, Consistência,
Isolamento e Durabilidade) para garantir a integridade dos dados.

### Eficiência na Escrita e Leitura: 
  - O formato delta é projetado para otimizar a eficiência na gravação e leitura de dados, tornando-o adequado para cenários
em que os dados são frequentemente atualizados.

### Suporte para Estruturas de Dados Complexas: 
 - Pode armazenar dados semi-estruturados e estruturados, como JSON ou Parquet, e é compatível com várias linguagens
de programação e ferramentas de processamento de dados.

### Apache Delta Lake: 
 - Uma das implementações mais conhecidas do formato delta é o Apache Delta Lake, que é uma camada de gerenciamento de dados que se integra
com ecossistemas de big data, como o Apache Spark. Ele adiciona recursos de controle de transações, garantias ACID e suporte a esquemas à camada de armazenamento de dados subjacente.

O formato delta é particularmente útil em cenários onde há uma necessidade de lidar com grandes volumes de dados que são frequentemente atualizados, como
em aplicações de análise em tempo real, ingestão de dados de streaming e processamento de dados em data lakes. Ele ajuda a garantir a consistência e a integridade dos dados, ao mesmo tempo que oferece eficiência na gravação e leitura de dados.
