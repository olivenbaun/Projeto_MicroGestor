# 5. Requisitos Não-Funcionais (RNFs)

Os Requisitos Não-Funcionais definem as qualidades, restrições e critérios operacionais que o MicroGestor deve satisfazer. Eles complementam o escopo funcional (HUs).

---

## 5.1. Performance e Desempenho (Rastreabilidade e Velocidade)

| ID | Requisito Não-Funcional (RNF) | Métrica | Racional (Por que é importante) |
| :--- | :--- | :--- | :--- |
| **RNF01** | O sistema deve responder à **Consulta de Saldo** de um Produto (RF10) rapidamente. | Tempo de resposta ≤ 1 segundo. | Garante que o **Operador (Fernando)** não perca tempo esperando e agiliza o fluxo de trabalho. |
| **RNF02** | O sistema deve carregar a **Dashboard com Alertas de Estoque Mínimo** (RF11). | Tempo de carregamento ≤ 2 segundos. | Essencial para que a **Encarregada de Compras (Amanda)** tenha visibilidade imediata das prioridades. |
| **RNF03** | As operações de **Registro de Entrada e Saída** devem ser rápidas para evitar interrupções no fluxo de trabalho. | Conclusão da transação ≤ 1 segundo após o clique. | Garante a alta usabilidade e incentiva o uso contínuo do sistema pelo Operador (Fernando). |

---

## 5.2. Segurança e Acesso (Rastreabilidade e Proteção)

| ID | Requisito Não-Funcional (RNF) | Métrica | Racional (Por que é importante) |
| :--- | :--- | :--- | :--- |
| **RNF04** | O acesso ao MicroGestor deve ser restrito através de **autenticação com login e senha** (RF14). | Criptografia de senhas (mínimo AES-256 ou similar). | Protege os dados sensíveis do inventário contra acesso não autorizado. |
| **RNF05** | O sistema deve manter um **registro (log) de todas as Movimentações** (Entrada/Saída), incluindo o **usuário que realizou a ação e o carimbo de data/hora**. | Rastreabilidade 100%. | Garante a auditoria dos dados de estoque, crucial para o **Administrador (José)** identificar responsáveis por erros. |
| **RNF06** | As diferentes **Perfis de Acesso** (Administrador, Compras, Operador) devem garantir que usuários sem permissão não possam executar funções críticas (ex: Operador não pode gerar Relatório de Custos). | Restrição de 100% de acesso. | Implementação direta da RF14, garantindo a integridade e a segregação de funções. |

---

## 5.3. Usabilidade e Interface (Foco no Usuário)

| ID | Requisito Não-Funcional (RNF) | Métrica | Racional (Por que é importante) |
| :--- | :--- | :--- | :--- |
| **RNF07** | A interface de **Registro de Entrada e Saída** deve ser intuitiva e adaptável a telas menores (smartphones/tablets). | Suporte a dispositivos móveis (design responsivo). | Permite que o **Operador (Fernando)** registre a movimentação diretamente no almoxarifado/local de uso. |
| **RNF08** | O sistema deve utilizar uma **terminologia consistente** em todas as telas. | Aderência total ao **Glossário (03_Glossario.md)**. | Reduz a curva de aprendizado e o risco de erros de interpretação por parte dos usuários. |
| **RNF09** | O sistema deve fornecer **mensagens claras de erro** ao usuário quando uma operação falhar (ex: tentativa de registrar Saída maior que o Saldo). | Mensagens de erro com indicação de correção. | Aumenta a autonomia do usuário e reduz a necessidade de suporte. |

---

## 5.4. Confiabilidade e Manutenibilidade

| ID | Requisito Não-Funcional (RNF) | Métrica | Racional (Por que é importante) |
| :--- | :--- | :--- | :--- |
| **RNF10** | Os dados de estoque devem ser armazenados de forma persistente e com **backup diário**. | Taxa de perda de dados ≤ 0.01% ao ano. | Garante a continuidade do negócio em caso de falha do servidor ou perda de dados. |
| **RNF11** | O sistema deve ser desenvolvido com **tecnologias atuais** e modularizadas, facilitando a adição futura de novas funcionalidades (ex: Controle de Lotes). | Baixo Acoplamento e Alta Coesão. | Prepara o sistema para evoluções futuras, como a solicitação da **Diretora Financeira (Claudia)**. |