# Projeto: Agendamento de Salas

Este documento detalha os requisitos funcionais e não funcionais para o sistema de controle e gestão de reservas de salas, desenvolvido como parte do Projeto Extensionista II.

## 1. Requisitos Funcionais (RF)

| ID | Nome | Descrição |
| :--- | :--- | :--- |
| **RF001** | Efetuar Login | O sistema deve permitir que os usuários realizem login informando e-mail/usuário e senha. |
| **RF002** | Cadastrar Usuários | O sistema deve permitir o cadastro de novos usuários com dados como nome, e-mail, senha e perfil de acesso (ex.: Usuário Comum, Administrador/Aprovador). |
| **RF003** | Controle de Acesso | O sistema deve restringir o acesso às funcionalidades com base no perfil do usuário (ex.: apenas Administradores aprovam reservas e cadastram salas). |
| **RF004** | Cadastrar Sala | O sistema deve permitir a inclusão de novas salas informando nome, tipo (Reunião, Biblioteca, Laboratório), capacidade e recursos disponíveis. |
| **RF005** | Listar e Editar Salas | O sistema deve permitir a listagem, edição dos dados e inativação de salas existentes. |
| **RF006** | Criar Reserva | O sistema deve permitir que o usuário solicite a reserva de uma sala, informando a sala desejada, data, horário de início e horário de término. |
| **RF007** | Verificar Disponibilidade | Regra Principal: O sistema deve validar se a sala já possui reserva confirmada ou pendente no mesmo intervalo de horário. Caso haja sobreposição, o agendamento deve ser bloqueado. |
| **RF008** | Cancelar Reserva | O sistema deve permitir que o usuário cancele sua própria reserva ou que o administrador cancele qualquer reserva existente. |
| **RF009** | Visualizar Calendário | O sistema deve exibir uma interface de calendário (diária, semanal e mensal) com o status das salas e agendamentos. |
| **RF010** | Filtrar Agendamentos | O sistema deve permitir a filtragem do calendário por tipo de sala, sala específica, data ou status da reserva. |
| **RF011** | Aprovação de Reservas | O sistema deve permitir que administradores/aprovadores aceitem ou recusem solicitações de reserva pendentes. |
| **RF012** | Notificação de Status | O sistema deve atualizar o status da reserva e enviar uma notificação por e-mail ao solicitante sempre que o status for alterado. |
| **RF013** | Histórico de Reservas | O sistema deve permitir a consulta do histórico de reservas, exibindo status passados, datas, horários e responsáveis. |
| **RF014** | Relatórios/Exportação | O sistema deve permitir gerar relatórios em PDF das reservas do mês. |
| **RF015** | Edição/Inativação de Usuários | O sistema deve permitir que o administrador altere dados e execute a inativação de contas de usuários, mantendo os dados para integridade do histórico. |

## 2. Requisitos Não Funcionais (RNF)

| ID | Nome | Descrição |
| :--- | :--- | :--- |
| **RNF001** | Tempo de Resposta | A verificação de conflito e confirmação do agendamento devem ser executadas em até 2 segundos. |
| **RNF002** | Acessos Simultâneos | O sistema deve suportar múltiplas requisições simultâneas sem gerar erros de duplicidade (race conditions). |
| **RNF003** | Criptografia | As senhas devem ser armazenadas utilizando algoritmos de hash seguros (ex.: bcrypt). |
| **RNF004** | Autenticação e Sessão | O sistema deve encerrar a sessão do usuário após 30 minutos de inatividade. |
| **RNF005** | Proteção de Dados | Apenas usuários autenticados devem ter acesso às telas do sistema e às APIs internas. |
| **RNF006** | Design Responsivo | A interface deve ser adaptável para desktops, tablets e smartphones . |
| **RNF007** | Facilidade de Uso | O fluxo para realizar uma reserva deve exigir no máximo 3 cliques a partir do calendário. |
| **RNF008** | Disponibilidade | O sistema deve manter um uptime de no mínimo 99% durante o horário comercial. |
| **RNF009** | Integridade de Dados | O banco de dados deve utilizar transações ACID para garantir que não ocorram reservas duplicadas simultâneas. |
| **RNF10** | Multiplataforma | O sistema deve ser acessível pelos navegadores Chrome, Firefox, Safari e Edge. |
| **RNF11** | Organização do Código | O código deve ser estruturado em camadas (interface, negócio, banco) para facilitar manutenção. |

## 3. Priorização dos Requisitos

### Essenciais
*Indispensáveis para a operação básica e resolução de conflitos.*
- **Funcionais:** RF01, RF02, RF04, RF06, RF07.

### Importantes
*Fundamentais para gestão, controle de acesso e experiência do usuário.*
- **Funcionais:** RF03, RF05, RF08, RF09, RF11, RF12, RF15.

### Desejáveis
*Otimizam o uso, mas não impedem o funcionamento inicial.*
- **Funcionais:** RF10, RF13, RF14.


