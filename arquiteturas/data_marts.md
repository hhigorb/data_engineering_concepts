# Data Marts

Data marts são pequenos repositórios de dados que são projetados para atender às necessidades específicas de um departamento ou equipe dentro de uma organização.
Eles são subconjuntos de um data warehouse maior e contêm dados relevantes para um grupo de usuários específico.

![Arquitetura Data Mart](../images/arquitetura_data_mart.png 'Arquitetura Data Mart')

Imagine que você trabalha em uma grande empresa de varejo. A empresa possui um data warehouse central que armazena todos os dados relacionados às vendas,
estoque, clientes e operações em toda a organização. No entanto, diferentes departamentos, como vendas, marketing e finanças, têm necessidades diferentes de análise de dados.

Para atender a essas necessidades específicas, a empresa cria data marts separados. Por exemplo:

**Data Mart de Vendas:** Este data mart contém apenas os dados relevantes para a equipe de vendas, como informações sobre vendas diárias, metas de vendas,
histórico de vendas de produtos específicos e desempenho das equipes de vendas.

**Data Mart de Marketing:** Aqui, estão armazenados os dados que os profissionais de marketing precisam, como dados sobre campanhas publicitárias,
análise de clientes, comportamento de compra e métricas de marketing.

**Data Mart Financeiro:** O departamento financeiro terá seu próprio data mart com informações sobre receitas, despesas, lucratividade, orçamento
e projeções financeiras.

Cada data mart é projetado para atender às necessidades específicas desses departamentos, tornando mais fácil para eles acessar e analisar os dados
relevantes sem precisar navegar pelo data warehouse completo. Isso agiliza a análise e tomada de decisões, permitindo que cada equipe tenha um acesso mais eficiente aos dados que são essenciais para suas operações.
