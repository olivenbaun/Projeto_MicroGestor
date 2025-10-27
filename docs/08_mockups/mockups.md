# 8. Wireframes (Mockups de Baixa Fidelidade)

Os Wireframes definem a estrutura, o layout e a hierarquia visual das telas mais críticas do MicroGestor, garantindo que os Requisitos Não-Funcionais de Usabilidade (RNF07, RNF08) sejam atendidos.

---

## 8.1. Paleta de Cores do MicroGestor

Esta paleta será utilizada para a identidade visual do sistema, com foco na clareza e no contraste.

| Nome da Cor | Código RGB (Red, Green, Blue) | Código HEX (Referência) | Função Principal no Sistema |
| :--- | :--- | :--- | :--- |
| **Azul Profundo** | rgb(1, 107, 186) | #016BB9 | Cor de Estrutura: Fundo de navegação, títulos de cards. |
| **Ciano Vibrante** | rgb(0, 206, 255) | #00CEFF | Cor Primária: Botões de ação, links, indicadores de estoque. |
| **Verde Limão** | rgb(108, 255, 0) | #6CFF00 | Cor de Sucesso/Alerta: Confirmações, alertas críticos de estoque. |
| **Branco (Fundo)** | rgb(255, 255, 255) | #FFFFFF | Fundo principal da área de conteúdo. |
| **Preto/Texto** | rgb(34, 34, 34) | #222222 | Textos e cores de alto contraste. |

---

## 8.2. Wireframe 1: Dashboard Principal (Visão Geral e Alertas)

Esta tela é o ponto de entrada e deve priorizar a visibilidade dos alertas e do saldo atual.

| Componente | Conteúdo / Design | Paleta de Cores | Relação com RF/RNF |
| :--- | :--- | :--- | :--- |
| **Barra Lateral (Navegação)** | Fundo em **Azul Profundo (#016BB9)**. Links diretos para todas as telas essenciais. **Ação Principal:** **Botão Logout** na parte inferior. | Azul Profundo, Botão de Logout contrastante (Ex: Ciano). | **RF14** (Acesso Seguro), RNF08 (Usabilidade). |
| **Card: Total em Estoque** | Exibe o saldo total de itens. | Fundo em **Ciano Vibrante (#00CEFF)**. | RF10 |
| **Card: Alertas Críticos** | Exibe a contagem de itens abaixo do Ponto de Reposição. | Fundo em **Verde Limão (#6CFF00)** (Alerta de Ação). | **RF11**, RNF02. |
| **Seção: Itens com Estoque Crítico** | Lista detalhada dos produtos em alerta (SKU, Saldo, Ponto Mínimo). | | RF11 |
| **Seção: Histórico de Movimentações** | Tabela com log recente de Entradas e Saídas (RNF05). | Tabela com cabeçalho em Azul Profundo. | RNF05. |

---

## 8.3. Wireframe 2: Tela de Cadastro de Produto (Foco em Integridade)

Esta tela é utilizada por Administrador/Compras (José/Amanda) e deve garantir o preenchimento correto dos dados.

| Componente | Conteúdo / Design | Relação com RF/RNF |
| :--- | :--- | :--- |
| **Título** | "Cadastro de Novo Produto" | RF01 |
| **Campo 1: Nome do Produto** | Campo de texto. **Obrigatório**. | RF01, RN01 |
| **Campo 2: Código de Referência (SKU)** | Campo de texto. **Obrigatório** e único. | RF01, RN02 |
| **Campo 3: Unidade de Medida (UdM)** | Lista suspensa (Ex: UN, KG, MT). | RF01 |
| **Campo 4: Ponto de Reposição** | Campo numérico (Estoque Mínimo). | RF02, RN03 |
| **Ações** | Botão "Salvar" (Ciano Vibrante - #00CEFF). | RF01 |

---

## 8.4. Wireframe 3: Tela de Registro de Entrada (Foco em Rastreabilidade e Custo)

Esta tela é utilizada por Compras (Amanda) e deve garantir a captura de dados de custo e fornecedor.

| Componente | Conteúdo / Design | Relação com RF/RNF |
| :--- | :--- | :--- |
| **Título** | "Registro de Entrada de Produtos" | RF05 |
| **Campo 1: Produto** | Campo de seleção com busca (autocomplete). | RF05 |
| **Campo 2: Quantidade Recebida** | Entrada numérica. | RF05 |
| **Campo 3: Preço Unitário de Compra** | Campo numérico de moeda (R$). | RF07 |
| **Campo 4: Fornecedor** | Campo de texto. | RF06 |
| **Campo 5: Data de Recebimento** | Campo de data. | RF06 |
| **Ações** | Botão "Confirmar Entrada" (Ciano Vibrante - #00CEFF). | RF05 |

---

## 8.5. Wireframe 4: Tela de Registro de Saída (Agilidade e Validação)

Esta tela é projetada para o Operador (Fernando), focada no fluxo rápido e na validação.

| Componente | Conteúdo / Design | Relação com RF/RNF |
| :--- | :--- | :--- |
| **Título** | "Registrar Saída de Produto" | RF08 |
| **Campo 1: Produto** | Campo de seleção que exibe o Saldo Atual. | RF08, RF10 |
| **Campo 2: Quantidade** | Entrada numérica. | RF08 |
| **Campo 3: Motivo da Saída** | Lista suspensa **obrigatória**. | RF09, RN09 |
| **Mensagem de Erro** | Exibição de erros de validação (ex: saldo negativo, RN08). | RNF09. |
| **Botão de Ação** | "Confirmar Saída" (Ciano Vibrante - #00CEFF). | RF08 |

---

## 8.6. Wireframe 5: Tela de Relatórios (Foco em Filtros)

Esta tela é utilizada por Claudia/José e deve ser flexível para gerar relatórios de saída e custo.

| Componente | Conteúdo / Design | Relação com RF/RNF |
| :--- | :--- | :--- |
| **Título** | "Geração de Relatórios" | RF12, RF13 |
| **Filtro 1: Tipo de Relatório** | Lista suspensa: "Saída por Período" (RF12) e "Custo de Itens Utilizados" (RF13). | RF12, RF13 |
| **Filtro 2: Data Inicial** | Campo de Data. | RN12 |
| **Filtro 3: Data Final** | Campo de Data. Validação: Data Final >= Data Inicial (RN12). | RN12 |
| **Ação** | Botão "Gerar Relatório" (Ciano Vibrante - #00CEFF). | RF12, RF13 |
| **Área de Visualização** | Tabela que exibe o resultado do relatório com opção de exportação. | RF12, RF13 |

---

## 8.7. Wireframe 6: Tela de Cadastro de Usuários (Foco em Segurança e Acesso)

Esta tela é de acesso exclusivo do Administrador (José) para gerenciar credenciais.

| Componente | Conteúdo / Design | Relação com RF/RNF |
| :--- | :--- | :--- |
| **Título** | "Cadastro e Gestão de Usuários" | RF14 |
| **Campo 1: Nome Completo** | Campo de texto. | Classe Usuário |
| **Campo 2: Login** | Campo de texto. Deve ser único. | RF14 |
| **Campo 3: Senha** | Campo de senha (oculta) com confirmação. | RF14, RNF04 |
| **Campo 4: Cargo/Perfil de Acesso** | Lista suspensa obrigatória: Administrador, Compras, Operador. | RF14 |
| **Ações** | Botão "Criar Usuário" (Ciano Vibrante - #00CEFF) e Tabela para **Editar/Excluir** usuários existentes. | RF14 |

---

## 8.8. Wireframe 7: Tela de Consulta de Produtos

Esta tela serve como o ponto central para pesquisa e manutenção dos produtos. As ações de edição/exclusão são restritas (RN04).

| Componente | Conteúdo / Design | Relação com RF/RNF |
| :--- | :--- | :--- |
| **Título** | "Consulta e Gestão de Produtos" | RF04, RF10 |
| **Campo de Busca** | Campo de texto principal que permite a busca por **Nome** ou **Código de Referência (SKU)**. | RF10, RNF01 |
| **Tabela de Resultados** | Lista os produtos que correspondem à busca. Colunas: SKU, Nome, UdM, **Saldo Atual** (RF10). | RF04, RF10 |
| **Botão de Ação Rápida** | **Novo Produto:** Botão grande para acesso rápido ao Cadastro (RF01). | |
| **Ações por Linha (Restritas)** | Botões "Editar" (RF03) e "Excluir". Visíveis **apenas** para perfis Administrador e Compras (RN04). | RF03, RF14, RN04 |

---