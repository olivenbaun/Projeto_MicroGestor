# 6. Regras de Negócio (RNs)

As Regras de Negócio definem as políticas, restrições e procedimentos específicos que governam o gerenciamento de inventário no MicroGestor. Elas devem ser estritamente implementadas para garantir a integridade dos dados.

---

## 6.1. Regras de Cadastro e Identificação (Base de Dados)

| ID | Regra de Negócio | Relação com RF | Racional |
| :--- | :--- | :--- | :--- |
| **RN01** | O campo **Nome do Produto** e o **SKU (Código de Referência)** são de preenchimento obrigatório no cadastro. | RF01 | Garante que todo produto seja identificável de forma unívoca. |
| **RN02** | O **SKU (Código de Referência)** deve ser único no sistema. Não é permitido cadastrar dois produtos com o mesmo SKU. | RF01 | Essencial para a rastreabilidade e integridade dos dados de estoque. |
| **RN03** | O **Ponto de Reposição (Estoque Mínimo)** deve ser um valor numérico inteiro (ou decimal, se a UdM for decimal) e deve ser maior ou igual a zero (0). | RF02 | Impede o cadastro de limites negativos ou inconsistentes. |
| **RN04** | A **Unidade de Medida (UdM)** não pode ser alterada após a primeira movimentação de estoque. | RF03 | Evita inconsistências na contagem do histórico de movimentação (ex: começar a contar em Kg e mudar para Unidade). |

---

## 6.2. Regras de Movimentação e Saldo (Integridade)

| ID | Regra de Negócio | Relação com RF | Racional |
| :--- | :--- | :--- | :--- |
| **RN05** | O saldo total de um **Produto** é calculado pela fórmula: **Saldo Inicial + Entradas - Saídas**. | RF05, RF08, RF10 | Define o algoritmo para o cálculo do saldo atual do inventário. |
| **RN06** | Toda **Movimentação** de estoque (Entrada ou Saída) deve ter a **Data e Hora da transação** registrada de forma imutável. | RF06, RNF05 | Garante a rastreabilidade das ações para fins de auditoria. |
| **RN07** | O **Registro de Saída** (baixa no estoque) **não pode ser efetuado** se a quantidade solicitada for maior que o **Saldo Atual** disponível do Produto. | RF08, RNF09 | Impede que o estoque fique negativo, forçando o controle físico do inventário. |
| **RN08** | O **Motivo da Saída** é de preenchimento obrigatório ao registrar a baixa de um Produto. | RF09 | Essencial para o cálculo de perdas e a geração correta do Relatório de Saída (RF12). |

---

## 6.3. Regras de Alerta e Relatórios (Decisão de Negócio)

| ID | Regra de Negócio | Relação com RF | Racional |
| :--- | :--- | :--- | :--- |
| **RN09** | Um **Alerta de Estoque Mínimo** (RF11) deve ser disparado e exibido na Dashboard sempre que o **Saldo Atual** de um Produto for **menor ou igual** ao seu **Ponto de Reposição**. | RF11 | Define a lógica booleana exata para acionamento do alerta (ação primária do sistema). |
| **RN10** | O **Relatório de Custos** (RF13) deve calcular o custo dos Produtos baixados utilizando o método de custo **FIFO (First-In, First-Out)** ou **Custo Médio Ponderado (CMP)**. *(Escolher um para o MVP)* | RF13 | Define o método contábil obrigatório para o cálculo de custos do inventário. **Sugestão: Custo Médio Ponderado é mais simples para o MVP.** |
| **RN11** | O sistema deve **validar** que a **data final** de um relatório (RF12, RF13) seja sempre **posterior ou igual** à **data inicial** selecionada pelo usuário. | RF12, RF13 | Impede que o usuário gere relatórios com parâmetros de data ilógicos ou invertidos. |

---