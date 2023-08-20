## Data Warehouse

Data Warehouse é um conceito utilizado para criar um repositório centralizado de informações. Todos os dados importantes da empresa são armazenados de forma organizada e estruturada. Dentro do Data Warehouse, os dados são agrupados em conjuntos, como dados de RH, financeiro, vendas, etc.

São projetados para dados estruturados, geralmente armazenados em bancos de dados relacionais. Eles são otimizados para desempenho de consulta e relatórios. São adequados para inteligência de negócios (BI) e análises, oferecendo ferramentas de consulta e relatório baseadas em SQL.

Fundamentos de Data Warehouse geralmente incluem compreender OLTP (Processamento de Transações Online), tabelas de dimensão, extração, transformação e carga (ETL), e modelagem de dados, como entender tabelas de fatos e dimensões.

No Data Warehouse, além de a estruturação dos dados ser organizada em conjuntos de dados específicos, conhecidos como Data Marts, é necessário definir como os dados serão armazenados.

Isso é feito através de uma modelagem de dados, onde são definidas as tabelas, colunas e os tipos dos dados que serão armazenados. Em um DW, primeiro você define o esquema de dados e depois você armazena os dados dentro do que foi especificado.

Diferente dos ambientes transacionais que possuem uma arquitetura OLTP onde o foco são as transações (inserir, alterar, deletar dados a todo momento), o Data Warehouse é um ambiente otimizado para consultas (uma arquitetura OLAP). É nesse conceito otimizado para consultas, com dados tratados, agregados/calculados e separado por categoria (Data Marts) em que são feitas as análises de negócios.

## Vantagens
  - Análise completa de dados, com precisão e histórico de dados anteriores;
  - Centralização de dados das mais diversas fontes de informação;
  - Aumento nas chances de assertividade no momento da tomada de decisões;
  - Maior eficiência na consulta aos dados.

## Desvantagens
  - Alto índice de problemas e imprevistos de grande complexidade.
  - Obsolescência;
  - Dificuldade na hora da integração do Data Warehouse com outros sistemas.


Consultas várias fontes para mais informações de estudos:

https://blog.xpeducacao.com.br/data-warehouse/

https://aws.amazon.com/pt/data-warehouse/
