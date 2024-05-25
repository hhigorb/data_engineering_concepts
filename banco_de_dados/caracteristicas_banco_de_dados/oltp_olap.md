# Ambientes OLTP e OLAP

## Qual é a diferença entre OLAP e OLTP?

O processamento analítico on-line (OLAP) e o processamento de transações on-line (OLTP) são sistemas de processamento de dados que ajudam você a armazenar e analisar dados
de negócios. As organizações coletam e armazenam dados de várias fontes, como sites, aplicativos, medidores inteligentes e sistemas internos. O OLAP combina e agrupa os
dados para que você possa analisá-los de diferentes pontos de vista. Por outro lado, o OLTP armazena e atualiza dados transacionais de forma confiável e eficiente em
grandes volumes. Os bancos de dados do OLTP podem ser uma das várias fontes de dados de um sistema OLAP.

Tanto o processamento analítico on-line (OLAP) quanto o processamento de transações on-line (OLTP) são sistemas de gerenciamento de banco de dados para armazenar e
processar dados em grandes volumes. Eles exigem uma infraestrutura de TI eficiente e confiável para funcionar sem problemas. Você pode usá-los para consultar dados
existentes ou armazenar novos dados. Ambos apoiam a tomada de decisão baseada em dados em uma organização.

A maioria das empresas usa os sistemas OLTP e OLAP juntos para atender aos requisitos de inteligência de negócios. No entanto, a abordagem e o propósito do gerenciamento
de dados diferem significativamente entre OLAP e OLTP.

## Principais diferenças: OLAP X OLTP

O objetivo principal do processamento analítico on-line (OLAP) é analisar dados agregados, enquanto o objetivo principal do processamento de transações on-line (OLTP)
é processar as transações do banco de dados.

Você usa sistemas OLAP para gerar relatórios, realizar análises complexas de dados e identificar tendências. Por outro lado, você usa sistemas OLTP para processar pedidos,
atualizar estoque e gerenciar contas de clientes.

Outras diferenças importantes incluem formatação de dados, arquitetura de dados, performance e requisitos. Também discutiremos um exemplo de quando uma organização
pode usar OLAP ou OLTP.

#### Formatação de dados

Os sistemas OLAP usam modelos de dados multidimensionais para que você possa visualizar os mesmos dados de diferentes ângulos. Os bancos de dados OLAP armazenam
dados em um formato de cubo, em que cada dimensão representa um atributo de dados diferente. Cada célula no cubo representa um valor ou medida para a interseção
das dimensões.

Os sistemas OLAP usam modelos de dados multidimensionais para que você possa visualizar os mesmos dados de diferentes ângulos. Os bancos de dados OLAP armazenam
dados em um formato de cubo, em que cada dimensão representa um atributo de dados diferente. Cada célula no cubo representa um valor ou medida para a interseção
das dimensões.

#### Arquitetura de dados

A arquitetura de banco de dados do OLAP prioriza a leitura de dados sobre as operações de gravação de dados. Você pode realizar consultas complexas de forma rápida
e eficiente em grandes volumes de dados. A disponibilidade é uma preocupação de baixa prioridade, pois o principal caso de uso é a análise.

Por outro lado, a arquitetura de banco de dados do OLTP prioriza as operações de gravação de dados. Ela é otimizada para workloads que exigem muita gravação e pode
atualizar dados transacionais de alta frequência e alto volume sem comprometer a integridade dos dados.

Por exemplo, se dois clientes comprarem o mesmo item ao mesmo tempo, o sistema OLTP pode ajustar os níveis de estoque com precisão. E o sistema priorizará o
primeiro cliente cronológico se o item for o último em estoque. A disponibilidade é uma alta prioridade e normalmente é obtida por meio de vários backups de dados.

#### Performance

Os tempos de processamento do OLAP podem variar de minutos a horas, dependendo do tipo e volume dos dados que estiverem sendo analisados. Para atualizar um banco
de dados OLAP, você processa periodicamente os dados em grandes lotes e, em seguida, carrega o lote no sistema de uma só vez. A frequência de atualização de dados
também varia entre os sistemas, de diária a semanal ou até mesmo mensal.

Por outro lado, você mede o tempo de processamento do OLTP em milissegundos ou menos. Os bancos de dados OLTP gerenciam as atualizações do banco de dados em
tempo real. As atualizações são rápidas, curtas e acionadas por você ou pelos seus usuários. O processamento de fluxo geralmente é usado em vez do processamento em lote.

#### Requisitos 

Os sistemas OLAP agem como um armazenamento de dados centralizado e extraem dados de vários data warehouses, bancos de dados relacionais e outros sistemas.
Os requisitos de armazenamento variam de terabytes (TB) a petabytes (PB). As leituras de dados também podem consumir muita computação, exigindo servidores
de alta performance.

Por outro lado, você pode medir os requisitos de armazenamento OLTP em gigabytes (GB). Os bancos de dados OLTP também podem ser apagados quando os dados
forem carregados em um data warehouse ou data lake relacionado ao OLAP. No entanto, os requisitos de computação para OLTP também são altos.

#### Exemplo de OLAP versus OLTP

Vamos considerar uma grande empresa de varejo que opera centenas de lojas em todo o país. A empresa tem um enorme banco de dados que rastreia as vendas,
o estoque, os dados de clientes e outras métricas importantes.

A empresa usa o OLTP para processar transações em tempo real, atualizar os níveis de estoque e gerenciar contas de clientes. Cada loja é conectada ao
banco de dados central, que atualiza os níveis de estoque em tempo real à medida que os produtos são vendidos. A empresa também usa o OLTP para gerenciar
contas de clientes, por exemplo, rastrear pontos de fidelidade, gerenciar informações de pagamento e processar devoluções.

Além disso, a empresa usa o OLAP para analisar os dados coletados pelo OLTP. Os analistas de negócios da empresa podem usar o OLAP para gerar relatórios
sobre tendências de vendas, níveis de estoque, dados demográficos de clientes e outras métricas importantes. Eles realizam consultas complexas em grandes
volumes de dados históricos para identificar padrões e tendências que possam servir para embasar as decisões de negócios. Eles identificam os produtos
mais conhecidos no mercado em um determinado período de tempo e usam as informações para otimizar os orçamentos para estoque.

## Quando usar OLAP versus OLTP

O processamento analítico on-line (OLAP) e o processamento de transações on-line (OLTP) são dois sistemas diferentes de processamento de dados
criados para finalidades diferentes. O OLAP é otimizado para análises e relatórios de dados complexos, enquanto o OLTP é otimizado para processamento
transacional e atualizações em tempo real.

Entender as diferenças entre esses sistemas pode ajudar você a tomar decisões informadas sobre qual sistema atende melhor às suas necessidades.
Em muitos casos, uma combinação dos sistemas OLAP e OLTP pode ser a melhor solução para empresas que exigem processamento de transações e análise
de dados. Em última análise, a escolha do sistema certo depende das necessidades específicas da sua empresa, incluindo volume de dados, complexidade
da consulta, tempo de resposta, escalabilidade e custo.

## Resumão entre OLTP e OLAP

![OLTP e OLAP](../../images/oltp_olap.png 'OLTP e OLAP')

Fonte: https://aws.amazon.com/pt/compare/the-difference-between-olap-and-oltp/
