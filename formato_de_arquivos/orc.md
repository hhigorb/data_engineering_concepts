# Arquivo ORC

O formato ORC, que significa "Optimized Row Columnar," é um formato de armazenamento de dados colunar usado principalmente em sistemas de processamento de big data, como o Apache Hive e o Apache Impala, que fazem parte do ecossistema Hadoop. Ele foi projetado para otimizar o armazenamento e recuperação de dados, tornando-o uma escolha popular em ambientes onde a eficiência de leitura e consulta é crítica.

## Vantagens do formato ORC:

### Compressão eficiente: 
  - O ORC utiliza algoritmos de compressão avançados, como o Zlib, para reduzir o tamanho dos dados armazenados. Isso economiza espaço em disco e melhora o desempenho de leitura, pois menos dados precisam ser transferidos da memória para a CPU.

### Esquema colunar: 
  - Diferentemente dos formatos de armazenamento de dados tradicionais, como o CSV, o ORC armazena os dados em colunas, em vez de linhas. Isso permite uma recuperação mais eficiente de dados durante as consultas, uma vez que apenas as colunas relevantes são lidas, economizando tempo e recursos.

### Poda de leitura: 
  - O formato ORC suporta a capacidade de "poda de leitura", o que significa que ele pode ignorar a leitura de partes irrelevantes dos dados durante a consulta. Isso é especialmente útil quando se trabalha com grandes conjuntos de dados, economizando tempo e recursos de CPU.

### Suporte a tipos de dados complexos: 
  - O ORC oferece suporte a tipos de dados complexos, como arrays e mapas, tornando-o adequado para armazenar dados semi-estruturados ou aninhados.

### Estatísticas avançadas: 
  - O ORC mantém estatísticas de coluna, como contagem de valores distintos e estatísticas de valores nulos, o que pode melhorar significativamente o desempenho das consultas ao permitir otimizações no planejamento da consulta.

## Desvantagens do formato ORC:

### Não é adequado para todas as situações: 
  - O ORC é altamente otimizado para leituras e consultas, mas pode não ser a melhor escolha para cargas de trabalho que envolvem muita escrita de dados, pois a otimização de gravação não é tão eficiente.

### Não é um formato humano-legível: 
  - Ao contrário de formatos como CSV ou JSON, o ORC não é legível por humanos, o que pode dificultar a visualização e a edição dos dados diretamente.

### Requer conversão: 
  - Se você já possui dados em outros formatos, pode ser necessário realizar a conversão para ORC, o que pode ser um processo demorado e exigir recursos adicionais.

Em resumo, o formato ORC é uma opção poderosa e eficiente para armazenar e consultar grandes volumes de dados em ambientes de big data. Suas vantagens incluem compressão eficiente, esquema colunar, suporte a tipos de dados complexos e estatísticas avançadas. No entanto, ele pode não ser a escolha ideal em todos os cenários e pode requerer conversão de dados existentes. Portanto, a escolha do formato de armazenamento deve ser baseada nas necessidades específicas do projeto e nos requisitos de desempenho.
