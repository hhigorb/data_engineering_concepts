# ACID

O ACID é um acrônimo usado para descrever as propriedades essenciais que garantem a consistência e a integridade das transações em um banco de dados. Cada letra representa uma característica importante:

- **Atomicidade (Atomicity)**
  - Significa que uma transação é uma operação única e indivisível. Ou seja, ou todas as partes da transação são executadas com sucesso, ou nenhuma delas é executada. Se alguma parte da transação falhar, o banco de dados retornará ao estado anterior (rollback), desfazendo todas as mudanças feitas até o momento.

- **Consistência (Consistency)**
  - Assegura que uma transação leva o banco de dados de um estado válido para outro estado válido. Isso significa que todas as regras e restrições do banco de dados devem ser seguidas durante a execução da transação, mantendo os dados em um estado coerente.

- **Isolamento (Isolation)**
  - Garante que as transações em execução sejam isoladas umas das outras, para que operem como se fossem executadas em série, mesmo que ocorram simultaneamente. Isso evita que uma transação interfira nos resultados de outra, mantendo a consistência dos dados.

- **Durabilidade (Durability)**
  - Depois que uma transação é concluída com sucesso, suas alterações se tornam permanentes e são armazenadas de forma duradoura no banco de dados. Isso significa que mesmo em caso de falhas de energia ou outros problemas, as mudanças não serão perdidas.

Em resumo, o ACID é um conjunto de propriedades que garantem que as transações em um banco de dados sejam executadas de forma confiável, mantendo a consistência dos dados e protegendo contra perdas de informações importantes.
