# Diferenças entre os formatos Avro, Parquet e ORC

## Modelo de Armazenamento:

**ORC:** 
  - O ORC é principalmente um formato de armazenamento colunar, mas suporta uma estrutura de linha interna para melhorar o desempenho de consultas que requerem dados de
várias colunas para uma única linha.
    
**Parquet:** 
  - O Parquet é estritamente um formato de armazenamento colunar.
    
**Avro:** 
  - O Avro é um formato de armazenamento de dados flexível e genérico que pode armazenar dados em registros serializados em formato binário. Ele não é estritamente colunar ou de linha,
mas oferece flexibilidade para estruturar dados conforme necessário.

## Compressão:

**ORC:**
  - O ORC usa técnicas de compressão otimizadas para a compactação de dados em colunas.
    
**Parquet:** 
  - O Parquet oferece compressão eficiente, mas as taxas de compressão podem variar dependendo dos dados e das configurações de compressão.
    
**Avro:** 
  - O Avro não possui otimizações específicas de compressão, embora seja possível aplicar compressão a dados Avro usando codecs como Snappy ou Gzip.
    
## Compatibilidade:

**ORC:** 
  - Amplamente suportado em ecossistemas do Hadoop, como Hive e Spark, mas pode ter suporte limitado em outras ferramentas.
    
**Parquet:**
  - Amplamente adotado e suportado em várias ferramentas e sistemas, incluindo Hadoop, Spark, Hive e muitos outros.
    
**Avro:** 
  - O Avro é compatível com muitas linguagens de programação e é usado em várias ferramentas e sistemas, embora não seja especificamente um formato de armazenamento colunar.

## Desempenho:

**ORC:** 
  - Desempenho superior em consultas analíticas que envolvem várias colunas, graças à sua estrutura híbrida de linha e coluna.

**Parquet:** 
  - Pode ter um desempenho igualmente bom em consultas que envolvem apenas um subconjunto de colunas, mas pode ser menos eficiente em consultas que exigem todas as colunas de uma linha.
    
**Avro:** 
  - O desempenho do Avro pode variar dependendo da estrutura dos dados e das operações de consulta. Não possui otimizações específicas de armazenamento colunar.
