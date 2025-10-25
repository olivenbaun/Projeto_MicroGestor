# 3. Glossário de Termos: MicroGestor MVP

Este glossário estabelece a terminologia padrão a ser utilizada em toda a documentação de requisitos, design e código do projeto MicroGestor, garantindo a comunicação clara entre todos os stakeholders.

| Termo | Definição |
| :--- | :--- |
| **MicroGestor** | Nome oficial do Produto Mínimo Viável (MVP): Sistema web de controle de inventário para pequenos estabelecimentos. |
| **Produto** | Qualquer item físico ou material que está sob controle do sistema. Pode ser uma mercadoria para revenda (varejo) ou matéria-prima/peça (serviço). |
| **Inventário / Estoque** | O volume total de **Produtos** disponíveis no estabelecimento em um determinado momento. |
| **SKU (Stock Keeping Unit)** | Um código de referência único atribuído a cada **Produto** para identificação e rastreabilidade no sistema. |
| **Unidade de Medida (UdM)** | A unidade pela qual o **Produto** é contado e movimentado no estoque (ex: Unidade, Kg, Metro, Litro). |
| **Ponto de Reposição / Estoque Mínimo** | O nível de estoque de um **Produto** que, ao ser atingido ou ultrapassado (abaixo), deve acionar um **Alerta de Estoque Mínimo**. |
| **Alerta de Estoque Mínimo** | Notificação visual no sistema, acionada automaticamente quando o saldo de um **Produto** atinge ou cai abaixo do **Ponto de Reposição**. |
| **Movimentação** | Qualquer transação que altere o saldo do **Inventário**. Inclui **Entrada** e **Saída** de **Produtos**. |
| **Registro de Entrada** | Ação de adicionar uma quantidade específica de um **Produto** ao estoque. Aumenta o saldo. |
| **Registro de Saída** | Ação de remover uma quantidade específica de um **Produto** do estoque. Diminui o saldo. |
| **Motivo da Saída** | A razão pela qual um **Produto** foi removido do estoque (ex: Venda, Uso Interno, Descarte/Perda). |
| **Fornecedor** | A entidade (pessoa ou empresa) de onde o **Produto** foi adquirido. Necessário para o **Registro de Entrada**. |
| **Dashboard** | A tela principal do sistema, que fornece uma visão consolidada e imediata do status do **Inventário**, incluindo os **Alertas de Estoque Mínimo**. |