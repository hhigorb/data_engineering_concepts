# Meta Dados

Os metadados são basicamente "dados sobre dados". Eles fornecem informações sobre as características de outros dados, ajudando a organizar, localizar e compreender informações sem precisar analisar todos os dados em si.

Por exemplo, considere uma foto digital. Além da imagem em si (os dados), a foto também pode ter metadados como data e hora da foto, modelo da câmera, configurações da câmera no momento da foto (como ISO, velocidade do obturador, abertura), possivelmente a localização geográfica onde a foto foi tirada e muito mais.

No contexto de um arquivo Parquet, que é um formato de armazenamento de colunas popular para processamento de big data, os metadados podem incluir informações como:

Schema: Uma descrição da estrutura dos dados, incluindo o nome e o tipo de cada coluna.
Estatísticas de coluna: Informações resumidas sobre os dados em cada coluna, como mínimo, máximo, contagem e soma.
Informações de localização: Onde no arquivo físico (ou em um conjunto de arquivos, se o Parquet for particionado) os dados para uma determinada linha ou coluna podem ser encontrados.
Metadados personalizados: Alguns sistemas permitem que os usuários adicionem seus próprios metadados para ajudar a rastrear informações adicionais.
Esses metadados permitem que os sistemas leiam e processem arquivos Parquet de forma mais eficiente. Por exemplo, eles podem usar as estatísticas de coluna para filtrar rapidamente partes irrelevantes de um arquivo sem precisar ler todos os dados. Ou eles podem usar o schema para entender como interpretar os dados brutos no arquivo.
