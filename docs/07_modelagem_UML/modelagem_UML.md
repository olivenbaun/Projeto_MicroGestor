# 7. Modelagem UML e Estrutura de Dados

## 7.1. Diagrama de Casos de Uso

O Diagrama de Caso de Uso (UC) mapeia as interações entre os usuários (Atores) e as funcionalidades principais do MicroGestor.

### 7.1.1. Atores e Casos de Uso (RFs Agrupados)

#### ➡️ Atores (Baseados nas Personas):

* **José (Administrador):** Acesso total, responsável pela gestão do sistema.
* **Amanda (Compras):** Responsável por compras e cadastro de itens (entrada).
* **Fernando (Operador):** Responsável pela utilização e baixa dos itens (saída).
* **Claudia (Diretora Financeira):** Usuária dos Relatórios.

#### ➡️ Casos de Uso (Agrupamento dos RFs):

| Caso de Uso | RFs Relacionados |
| :--- | :--- |
| **Gerenciar Produto** | RF01, RF02, RF03 |
| **Consultar Estoque** | RF04, RF10 |
| **Registrar Entrada** | RF05, RF06, RF07 |
| **Registrar Saída** | RF08, RF09 |
| **Visualizar Alertas** | RF11 |
| **Gerar Relatórios** | RF12, RF13 |
| **Gerenciar Acesso** | RF14 |

### 7.1.2. Mapeamento dos Casos de Uso e Atores

A tabela abaixo define quem pode executar cada ação no sistema, detalhando as permissões da RF14.

| Caso de Uso | José (Admin) | Amanda (Compras) | Fernando (Operador) | Claudia (Financeira) |
| :--- | :--- | :--- | :--- | :--- |
| **Gerenciar Produto** | ✅ | ✅ | ❌ | ❌ |
| **Consultar Estoque** | ✅ | ✅ | ✅ | ✅ |
| **Registrar Entrada** | ✅ | ✅ | ❌ | ❌ |
| **Registrar Saída** | ✅ | ❌ | ✅ | ❌ |
| **Visualizar Alertas** | ✅ | ✅ | ❌ | ❌ |
| **Gerar Relatórios** | ✅ | ❌ | ❌ | ✅ |
| **Gerenciar Acesso** | ✅ | ❌ | ❌ | ❌ |

---



## 7.2. Diagrama de Classes (Modelo de Dados)

O Diagrama de Classes representa as entidades principais do MicroGestor, seus atributos (dados) e os relacionamentos entre elas, fundamentando a estrutura do banco de dados.

### 7.2.1. Entidades Principais e Atributos

| Classe | Atributos (Dados Relevantes) | Relação com RF/RN |
| :--- | :--- | :--- |
| **Produto** | id (PK), SKU (String, Único, RN02), Nome (String, RN01), UdM (String, RN04), PontoReposicao (Decimal, RN03), SaldoAtual (Decimal, RN06) | RF01, RF02, RF10 |
| **Movimentacao** | id (PK), Tipo (String: Entrada/Saída), Quantidade (Decimal), DataHora (DateTime, RN07), Motivo (String, RN09) | RF05, RF08 |
| **TransacaoEntrada** | id (PK), PrecoUnitarioCompra (Decimal), Fornecedor (String), DataRecebimento (Date, RF06) | RF07 |
| **TransacaoSaida** | id (PK), CustoTotal (Decimal), MotivoSaida (String, RN09) | RF09, RF13 |
| **Usuario** | id (PK), Login (String, Único), SenhaHash (String, RNF04), PerfilAcesso (String: Admin, Compras, Operador), NomeCompleto | RF14 |

### 7.2.2. Relacionamentos entre Classes

O sistema é baseado no conceito de herança e associação para rastrear as transações de inventário.

1.  **Movimentacao é Abstrata:** A classe `Movimentacao` é generalizada. As classes `TransacaoEntrada` e `TransacaoSaida` herdam dela.
2.  **Relação Produto <> Movimentacao:**
    * Um `Produto` pode ter muitas `Movimentacoes` (Entrada ou Saída).
    * Uma `Movimentacao` pertence a um único `Produto`.
    * Relação: 1:N (um para muitos).
3.  **Relação Usuario <> Movimentacao:**
    * Um `Usuario` pode realizar muitas `Movimentacoes`.
    * Uma `Movimentacao` é realizada por um único `Usuario`.
    * Relação: 1:N (essencial para RNF05 - Log de Auditoria).

---



## 7.3. Diagrama de Atividades: Registro de Saída de Produto (RF08)

Este diagrama detalha o fluxo de trabalho passo a passo para o **Operador (Fernando)** registrar a baixa de um Produto do estoque, incluindo as validações críticas definidas nas Regras de Negócio (RNs).

### 7.3.1. Pool e Swimlanes

O diagrama será dividido em duas *swimlanes* (raias): **Operador (Fernando)** e **Sistema MicroGestor**.

### 7.3.2. Fluxo de Atividades

O fluxo foca na validação da quantidade para evitar saldo negativo (RN08) e na obrigatoriedade do Motivo de Saída (RN09).

1.  **Início:** Operador acessa a tela de Registro de Saída.
2.  **Operador:** Seleciona o Produto e informa a Quantidade a ser removida.
3.  **Sistema:** Verifica se a Quantidade a ser removida é maior que o Saldo Atual (RN08).
4.  **Decisão (RN08):**
    * **Se SIM (Quantidade > Saldo):** O Sistema exibe uma Mensagem de Erro (RNF09) e o Operador deve corrigir a quantidade. O fluxo retorna ao passo 2.
    * **Se NÃO (Quantidade ≤ Saldo):** O fluxo segue.
5.  **Sistema:** Verifica se o Motivo da Saída foi informado (RN09).
6.  **Decisão (RN09):**
    * **Se NÃO:** O Sistema exibe Mensagem de Erro. O fluxo retorna ao Operador para preencher o campo obrigatório.
    * **Se SIM:** O fluxo segue.
7.  **Sistema:** Processa a transação e atualiza o Saldo Atual do Produto (RN06).
8.  **Fim:** O Registro de Saída é concluído.

---



## 7.4. Diagrama de Sequência: Validação e Registro de Saída (RF08)

Este diagrama detalha a sequência cronológica de interações e mensagens entre as camadas de arquitetura (Frontend, Backend/API, Banco de Dados) para executar e validar um Registro de Saída de Produto.

### 7.4.1. Lifelines (Objetos Principais)

1.  **Operador (Fernando):** O Ator que inicia a ação.
2.  **Frontend (React UI):** A interface do usuário que coleta os dados.
3.  **Backend/API (Node.js):** O Controlador que executa a lógica de negócio (RNs).
4.  **Banco de Dados (PostgreSQL):** Onde os dados de Produto e Movimentação são armazenados e consultados.

### 7.4.2. Fluxo de Sequência (Processo de Baixa)

O foco é na **validação da quantidade solicitada (RN08)** antes da gravação dos dados.

1.  **Operador (Fernando)** envia o formulário de Saída (Produto ID, Quantidade, Motivo) através do Frontend.
2.  **Frontend** envia uma requisição `POST /saida` para a **API (Backend)**.
3.  **Backend** recebe a requisição e primeiro consulta o **Banco de Dados** para obter o **`SaldoAtual`** do Produto.
4.  **Banco de Dados** retorna o `SaldoAtual`.
5.  **Backend** executa a validação crítica: `Se (QuantidadeSolicitada > SaldoAtual)`? (RN08)
    * **Caminho Crítico (Falha):** Se SIM, o **Backend** retorna um `Status 400 (Bad Request)` com a mensagem de erro (RNF09). O **Frontend** exibe essa mensagem ao **Operador**.
    * **Caminho de Sucesso:** Se NÃO, o **Backend** prossegue para a gravação da `TransacaoSaida` e a atualização do `SaldoAtual` no **Banco de Dados**.
6.  **Banco de Dados** executa o *commit* da transação.
7.  **Backend** retorna um `Status 201 (Created)` ao **Frontend**.
8.  **Frontend** exibe a confirmação de sucesso ao **Operador**.

### 7.4.3. Representação Gráfica

. 6. Se falha, Backend retorna 400 para Frontend e este exibe erro. 7. Se sucesso, Backend envia instrução para Gravar Transação e Atualizar Saldo no Banco de Dados. 8. Banco de Dados confirma. 9. Backend retorna 201 para Frontend, que exibe sucesso ao Operador.

---