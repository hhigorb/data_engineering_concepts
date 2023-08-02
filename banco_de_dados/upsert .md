# Upsert

Upsert é uma operação que combina "update" (atualização) com "insert" (inserção). Em termos simples, o upsert permite que você atualize os dados de um registro se ele já existir em um banco de dados, ou insira um novo registro se ele não existir.

A ideia por trás do upsert é evitar a duplicação de dados e simplificar o processo de atualização das informações em um banco de dados. Quando você precisa adicionar novos dados ou atualizar informações existentes, o upsert se torna muito útil.

Por exemplo, suponha que você tenha um banco de dados com informações sobre clientes. Se um cliente já estiver registrado e desejar atualizar seu endereço, você pode usar a operação de upsert para verificar se o registro do cliente já existe no banco de dados. Se existir, você atualiza o endereço. Caso contrário, você cria um novo registro com os detalhes fornecidos.

Em resumo, o upsert é uma maneira prática de garantir que seus dados sejam consistentes, evitando duplicações e facilitando a inserção ou atualização de informações no banco de dados de forma eficiente.
