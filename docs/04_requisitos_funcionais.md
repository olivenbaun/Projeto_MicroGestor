# 4. Backlog de Requisitos Funcionais (Histórias de Usuário - RFs)

Este backlog lista as funcionalidades essenciais do MicroGestor MVP, priorizadas com base nas necessidades das Personas definidas e no escopo acordado. Todos os requisitos são apresentados no formato padrão de História de Usuário.

---

## 4.1. Seção 1: Gestão de Produtos (Cadastro)

| ID | Persona | História de Usuário (HU) |
| :--- | :--- | :--- |
| **RF01** | José ou Amanda | Como **Administrador/Encarregada de Compras**, eu quero **cadastrar um novo Produto**, para que ele possa ser movimentado e rastreado no inventário. |
| **RF02** | José ou Amanda | Como **Administrador/Encarregada de Compras**, eu quero **especificar o Ponto de Reposição (Estoque Mínimo)** ao cadastrar um produto, para que o sistema me alerte quando o nível de estoque estiver baixo. |
| **RF03** | José ou Amanda | Como **Administrador/Encarregada de Compras**, eu quero **editar os dados de um Produto** (Nome, SKU, UdM, Ponto de Reposição), para corrigir erros ou atualizar informações. |
| **RF04** | José ou Amanda | Como **Administrador/Encarregada de Compras**, eu quero **visualizar uma lista completa de todos os Produtos cadastrados**, para ter uma visão geral do que está no catálogo. |

---

## 4.2. Seção 2: Movimentação de Estoque (Entrada)

| ID | Persona | História de Usuário (HU) |
| :--- | :--- | :--- |
| **RF05** | Amanda | Como **Encarregada de Compras**, eu quero **registrar a Entrada de Produtos no estoque**, para que o saldo seja atualizado. |
| **RF06** | Amanda | Como **Encarregada de Compras**, eu quero **informar o Fornecedor e a Data de Recebimento** ao registrar uma entrada, para manter a rastreabilidade da compra. |
| **RF07** | Amanda | Como **Encarregada de Compras**, eu quero **registrar o Preço Unitário de Compra** ao dar entrada no produto, para que o custo de estoque e os relatórios financeiros futuros sejam corretos. |

---

## 4.3. Seção 3: Movimentação de Estoque (Saída)

| ID | Persona | História de Usuário (HU) |
| :--- | :--- | :--- |
| **RF08** | Fernando | Como **Operador**, eu quero **registrar a Saída de Produtos do estoque**, para que o saldo seja atualizado e reflita o consumo real. |
| **RF09** | Fernando | Como **Operador**, eu quero **selecionar o Motivo da Saída** (ex: Venda, Uso Interno, Descarte), para que a gestão possa analisar o consumo e as perdas. |

---

## 4.4. Seção 4: Consultas e Alertas (Visibilidade)

| ID | Persona | História de Usuário (HU) |
| :--- | :--- | :--- |
| **RF10** | Fernando | Como **Operador**, eu quero **consultar o Saldo atual de um Produto específico**, para saber se ele está disponível antes de ir buscá-lo. |
| **RF11** | Amanda | Como **Encarregada de Compras**, eu quero **visualizar todos os Produtos que estão abaixo do Ponto de Reposição (Alerta)**, para saber imediatamente o que precisa ser comprado. |

---

## 4.5. Seção 5: Relatórios e Acesso (Gerenciais)

| ID | Persona | História de Usuário (HU) |
| :--- | :--- | :--- |
| **RF12** | Claudia/José | Como **Diretora Financeira/Administrador**, eu quero **gerar um Relatório de Saída de Produtos**, especificando um período de tempo, para analisar o consumo e o giro do inventário. |
| **RF13** | Claudia/José | Como **Diretora Financeira/Administrador**, eu quero **gerar um Relatório de Custos dos Produtos utilizados** no período, para fazer a conciliação do gasto de inventário com o orçamento. |
| **RF14** | José | Como **Administrador**, eu quero que o sistema exija **login e senha** e utilize **perfis de acesso** (Administrador, Compras, Operador), para garantir que cada usuário só possa executar as ações permitidas à sua função. |

---
