# 1. Visão e Escopo do Produto: MicroGestor MVP

## 1.1. Contexto do Projeto

Este projeto consiste no desenvolvimento do **MicroGestor**, um Produto Mínimo Viável (MVP) que visa digitalizar e otimizar a gestão de inventário em **pequenos estabelecimentos comerciais ou de serviços (minimercados, oficinas mecânicas, pequenas lojas de varejo, etc.)**.

Atualmente, muitos desses pequenos negócios dependem de métodos manuais (planilhas ou cadernos), o que resulta em erros de contagem, falta inesperada de produtos e ineficiência operacional. O MicroGestor propõe uma solução simples e focada para resolver o problema de visibilidade e reposição de inventário.

## 1.2. Declaração da Visão do Produto

**Para** pequenos empresários e gerentes de estoque/almoxarifado de estabelecimentos comerciais ou de serviços (o público-alvo),
**Que** sofrem com perdas operacionais devido ao controle de inventário manual e ineficiente (a necessidade),
**O MicroGestor** é um sistema web simples e acessível (o nome e a categoria do produto),
**Que** permite o registro rápido de entradas e saídas e a emissão de alertas de reposição automáticos (o benefício principal),
**Diferentemente** das planilhas genéricas e sistemas ERP complexos (a alternativa),
**Nosso produto** oferece uma interface intuitiva focada apenas na visibilidade do estoque mínimo e na prevenção de rupturas de inventário (o principal diferencial).

## 1.3. Objetivos de Negócio (Metas do MVP)

O lançamento deste MVP deve atingir os seguintes objetivos de negócio em um curto prazo de validação:

1.  **Redução de Perdas Operacionais:** Diminuir em 20% os incidentes de falta de **Produto** no ponto de venda/uso (ruptura de estoque) nos primeiros 3 meses de uso.
2.  **Eficiência:** Reduzir em 50% o tempo gasto pelo operador de estoque na contagem e checagem de **Produtos** essenciais.
3.  **Validação de Usabilidade:** Receber feedback positivo (nota acima de 4/5) da Persona-alvo sobre a facilidade de registrar a movimentação (entrada/saída).

## 1.4. Escopo do MVP (O que está incluído)

O escopo do Mínimo Produto Viável (MVP) será estritamente limitado ao **Controle de Produtos** e às funcionalidades críticas que resolvem o problema central:

| Funcionalidade | Descrição Detalhada |
| :--- | :--- |
| **Sistema de Autenticação** | A autenticação do sistema deve identificar o usuário e dar-lhe as permissões necessárias para desempenhar sua função dentro do sistema (conforme definido nas Personas). |
| **Cadastro de Produto (Simples)** | Permite cadastrar um **Produto** com Nome, Código de Referência (SKU), Unidade de Medida e Ponto de Reposição (Estoque Mínimo). |
| **Registro de Entrada** | Permite adicionar **Produtos** ao inventário (compra/recebimento) com indicação de Fornecedor, Data e **Preço Unitário de Compra** (para fins de custo). |
| **Registro de Saída** | Permite remover **Produtos** do inventário (venda/uso em serviço/descarte) com indicação de Motivo. |
| **Consulta de Saldo** | Dashboard simples que exibe o saldo atual de cada **Produto**. |
| **Alerta de Estoque Mínimo** | Sistema que sinaliza automaticamente (na dashboard) quando um **Produto** atinge ou ultrapassa o Ponto de Reposição. |
| **Relatório de Saída de Produtos por Período** | O sistema é capaz de gerar relatórios periódicos quanto ao consumo/saída dos **Produtos** em estoque. |
| **Relatório de Custos** | O sistema é capaz de gerar relatório contendo os **custos dos Produtos utilizados** em período pré-definido (baseado no Preço Unitário de Compra registrado). |

---

## 1.5. Exclusões do Escopo do MVP (O que NÃO está incluído)

Para manter o produto mínimo e viável, as seguintes funcionalidades e componentes **NÃO FARÃO PARTE** desta primeira versão:
  
1.  **Múltiplos Armazéns/Lojas:** O MVP focará no estoque de um **único local**.
2.  **Controle de Validade/Lotes:** Não será controlada a data de vencimento dos produtos.
3.  **Integração com PDV (Ponto de Venda):** As saídas deverão ser registradas manualmente.
4.  **Relatórios de Projeção/Previsão:** Não serão incluídas análises preditivas (ex: Relatório de Giro de Estoque, Sugestão Automática de Compras Futuras).
