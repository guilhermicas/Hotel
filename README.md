# Projeto Hotel

O projeto é dividido em duas aplicações. Uma aplicação web estritamente para clientes, e uma aplicação WPF estritamente para o Hotel.

# Aplicação local do Hotel

A parte do Hotel terá dois niveis de acesso:

- Administrador
- Funcionario

Funcionalidades funcionario e Administrador:

- [ ] Login/Registo
- [ ] Efetuar Reservas
  - [ ] Efetuar registo de um cliente
  - [ ] Escolha do range de datas para reserva (pode se forçar uma range além da definida nas configuracoes, mas é necessessário confirmação da ação)
  - [ ] Escolha de categoria da reserva
  - [ ] Marcar uma reserva
  - [ ] Cancelar uma reserva
  - [ ] Re-schedule de uma reserva
  - [ ] Visualizar histórico de reservas
- [ ] Confirmar Check-in
- [ ] Gerir Quartos
  - [ ] Marcar quartos como inutilizavel temporariamente

Funcionalidades Administrador:

- [ ] Gerir funcionarios
  - [ ] Gerir categorias de funcionarios(que altera os niveis de acesso)
  - [ ] Inserir funcionarios
  - [ ] Atualizar funcionarios
  - [ ] Soft-delete funcionarios
  - [ ] Visualizar ações de funcionários
  - [ ] Visualizar informações guardadas do funcionário
- [ ] Gerir Quartos
  - [ ] Marcar quartos como inutilizavel temporariamente
  - [ ] Atribuir categoria a um range de quartos(todos os quartos para poderem ser utilizados têm de ter uma categoria associada)
- [ ] Gerir configuracoes gerais
  - [ ] Quantos quartos tem o Hotel
  - [ ] Qual o maior range de uma reserva

### Hotel workflow

Um cliente dirige-se ao Hotel e pode efetuar uma reserva. Para o registo da reserva é necessessário uma conta cliente, que pode ser criada no local por um funcionário ou pode já ter sido criada préviamente no site ou numa reserva no passado.
No dia da reserva o cliente pode se dirigir ao hotel e confirmar os dados para check-in.

# Site para clientes

Funcionalidades cliente:

- [ ] Login/Registo
- [ ] Reserva
  - [ ] Marcar uma reserva
  - [ ] Cancelar uma reserva
  - [ ] Re-schedule de uma reserva
  - [ ] Visualizar histórico de reservas
  - [ ] Visualização de quanto tempo falta para a próxima reserva
- [ ] Conta
  - [ ] Poder requisitar criação de palavra passe para poder utilizar conta no site caso se tenha registado no local sem dar email
  - [ ] Atualizar informações da conta
  - [ ] Apagar conta

### Cliente workflow

Um cliente pode criar uma conta e efetuar uma reserva
