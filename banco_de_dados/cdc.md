# CDC (Change Data Capture)

Change Data Capture (CDC) é uma técnica utilizada em bancos de dados para identificar e capturar as mudanças feitas nos dados de forma contínua e automática. Em termos simples, o CDC é como um "espião" que monitora as alterações que acontecem nos dados em um banco de dados.

Imagine que você tem um banco de dados com várias tabelas e registros, e várias operações estão acontecendo constantemente, como inserções, atualizações e exclusões de dados. O CDC observa essas operações à medida que ocorrem e registra as mudanças que acontecem em uma estrutura especial.

Essa estrutura especial geralmente é chamada de log de alterações (change log) ou log de transações. Nesse log, as mudanças são registradas de forma organizada, incluindo informações sobre o tipo de operação realizada (inserção, atualização ou exclusão), os dados envolvidos e o momento em que ocorreram.

O CDC tem diversas aplicações, sendo uma delas a replicação de dados. Por exemplo, suponha que você tenha um banco de dados central em um local e queira manter uma cópia atualizada desse banco em outro local. O CDC é usado para capturar as mudanças feitas no banco de dados central e replicá-las automaticamente para o banco de dados secundário, garantindo que ambas as bases de dados permaneçam sincronizadas.

Além disso, o CDC pode ser útil em análises em tempo real, auditoria de dados e outras situações em que é importante rastrear as mudanças nos dados de forma eficiente e precisa. Em resumo, o Change Data Capture é uma técnica valiosa para acompanhar as mudanças em bancos de dados e garantir a integridade e a consistência das informações.
