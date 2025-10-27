# 9. Matriz de Rastreabilidade de Requisitos

A Matriz de Rastreabilidade garante que cada Requisito Funcional (RF) do Backlog está vinculado a uma ou mais Personas, a Requisitos Não-Funcionais (RNF) e a Regras de Negócio (RN), assegurando que o produto final resolva as necessidades de negócio de forma completa e com qualidade.

---

| ID (RF) | Funcionalidade | Personas Relacionadas | Regras de Negócio (RNs) | Requisitos Não-Funcionais (RNFs) |
| :--- | :--- | :--- | :--- | :--- |
| **RF01** | Cadastro de Produto | José, Amanda | RN01, RN02, RN03 | RNF04 (Segurança) |
| **RF02** | Especificar Ponto de Reposição | José, Amanda | RN03, RN10 | RNF04 (Segurança) |
| **RF03** | Edição de Dados de Produto | José, Amanda | RN04, RN05 | RNF06 (Permissão) |
| **RF04** | Visualizar Lista de Produtos | Todos | Nenhuma | RNF07 (Usabilidade) |
| **RF05** | Registrar Entrada | Amanda, José | RN06 | RNF03 (Velocidade) |
| **RF06** | Informar Fornecedor/Data | Amanda, José | RN07 | RNF05 (Auditoria) |
| **RF07** | Registrar Preço Unitário | Amanda, José | RN06, RN11 | RNF05 (Auditoria) |
| **RF08** | Registrar Saída | Fernando, José | RN06, RN08 | RNF03 (Velocidade), RNF07 (Móvel) |
| **RF09** | Selecionar Motivo da Saída | Fernando, José | RN09 | RNF05 (Auditoria) |
| **RF10** | Consultar Saldo | Todos | RN06 | RNF01 (Performance), RNF07 (Móvel) |
| **RF11** | Alerta de Estoque Mínimo | Amanda, José | RN10 | RNF02 (Velocidade), RNF07 (Visual) |
| **RF12** | Relatório de Saída | Claudia, José | RN09, RN12 | RNF04, RNF06 (Segurança) |
| **RF13** | Relatório de Custos | Claudia, José | RN06, RN11, RN12 | RNF04, RNF06 (Segurança) |
| **RF14** | Sistema de Autenticação/Perfis | Todos | RN04, RN06 | RNF04, RNF06 (Segurança Crítica) |

---


## Documentação do Projeto **MicroGestor MVP** em fases.

**Fase 1: Concepção**
1.  `01_Visao_Escopo.md`
2.  `02_Personas.md`
3.  `03_Glossario.md`

**Fase 2: Especificação**
4.  `04_Requisitos_funcionais.md` (Backlog dos Requisitos Funcionais)
5.  `05_Requisitos_Nao_Funcionais.md`
6.  `06_Regras_de_Negocio.md`

**Fase 3: Modelagem e Design**
7.  `07_Modelagem_UML.md` (Casos de Uso, Classes, Atividades, Sequência)
8.  `08_Wireframes.md` (Mockups e Paleta de Cores)
9.  `09_Matriz_Rastreabilidade.md`
