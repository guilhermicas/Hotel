# Projeto Hotel

O projeto é dividido em duas aplicações. Uma aplicação web estritamente para clientes, e uma aplicação WPF estritamente para o Hotel.

# Aplicação local do Hotel

A parte do Hotel terá dois niveis de acesso:

- Administrador
- Funcionario

Funcionalidades funcionario e Administrador:

- [ ] Login/Registo
      SELECT username, password FROM Funcionarios WHERE username="%s" AND password="%s";

- [ ] Opções do Menu Reservas

  - [ ] Efetuar uma reserva

    - [ ] pode efetuar registo de um cliente
          INSERT INTO Clientes (idFuncionario, nome, email, NIF, telefone) VALUES ()
    - [ ] Lookup de clientes para reutilizar conta ja previamente inserida caso seja o caso ou para atualizar os dados
    - [ ] Escolha do range de datas para reserva (pode se forçar uma range além da definida nas configuracoes, mas é necessário confirmação da ação)(funcionalidade imbutida)
    - [ ] Escolha de categoria da reserva
          INSERT INTO Reservas (idCliente, idFuncionario, numeroQuarto, dataInicial, dataFinal, cancelada) VALUES ()
    - [ ] Escolha opcional de pacotes extra (almoço, wifi, wtv..)

  - [ ] Re-schedule de uma reserva
        UPDATE Reservas SET dataInicial=%d, dataFinal=%d WHERE ()

  - [ ] Confirmar Check-in
        UPDATE Reservas SET checkedIn=1 WHERE id=%d

  - [ ] Visualizar histórico de reservas(funcionalidade principal)
        SELECT \* FROM Reservas [WHERE ...]

    - [ ] Re-schedule de reserva

    - [ ] Cancelar uma reserva(funcionalidade imbutida)
          Ao cancelar uma reserva, pode se escolher mandar um e-mail/mensagem para informar/confimar a cancelação da reserva
          UPDATE Reservas SET cancelada=1 WHERE id = %d
    - [ ] Atribuição de pacotes extra na reserva
          INSERT INTO Extras (idReserva, idPacote) VALUES

  - [ ] Visualizar reservas atualmente ativas

    - [ ] Atribuição de pacotes extra na reserva
          INSERT INTO Extras (idReserva, idPacote) VALUES

  - [ ] Opções Menu de gestão de quartos
    - [ ] Marcar quartos como inutilizavel temporariamente
          INSERT INTO QuartosIndisponives (idFuncionario, numeroQuarto, motivo, data_ocorrencia) VALUES ()

Funcionalidades Administrador:

- [ ] Opções Menu de funcionarios
  - [ ] Inserir funcionarios
        INSERT INTO Funcionarios (nome, password, data_nascimento, deletado, data) VALUES ()
  - [ ] Atualizar funcionarios
        UDPATE Funcionarios
  - [ ] Soft-delete funcionarios
        UDPATE Funcionarios SET deletado=1 WHERE id=%d
  - [ ] Visualizar ações de funcionários
        SELECT \* FROM [Reservas, Clientes, QuartosIndisponives] [WHERE idFuncionario = %d]
  - [ ] Visualizar informações guardadas do funcionário
        SELECT \* FROM Funcionario WHERE id = %d
- [ ] Opções Menu de gestão de quartos
  - [ ] Atribuir categoria a um range de quartos(todos os quartos para poderem ser utilizados têm de ter uma categoria associada)
        (ter em conta que um range tem de começar onde o outro acabar)
        INSERT INTO RangesQuartos
- [ ] Gestão de pacotes(wifi, almoço, etc)
      INSERT INTO Pacotes (titulo, descricao, preco) VALUES ()
- [ ] Gerir configuracoes gerais
      Ficheiro de configuração local
  - [ ] Quantos quartos tem o Hotel
  - [ ] Qual o maior range de uma reserva

detalhes:
Se um utilizador tiver uma reserva e nao aparecer no dia do check in, aparecer notificação.
Sempre que se for fazer uma tarefa de nivel de acesso maior, verificar se a conta é admin (nem que seja para visualizar dados) se nao for atualizar aq aplicação devidamente

### Hotel workflow

Um cliente dirige-se ao Hotel e pode efetuar uma reserva. Para o registo da reserva é necessessário uma conta cliente, que pode ser criada no local por um funcionário ou pode já ter sido criada préviamente no site ou numa reserva no passado.
No dia da reserva o cliente pode se dirigir ao hotel e confirmar os dados para check-in.

# Site para clientes

Funcionalidades cliente:

- [ ] Login/Registo
      SELECT email, password FROM Clientes WHERE email="%s" password="%s"
      [ ] Reserva
  - [ ] Marcar uma reserva
        INSERT INTO Reservas ()
  - [ ] Cancelar uma reserva
  - [ ] Re-schedule de uma reserva
  - [ ] Visualizar histórico de reservas
        SELECT \* FROM Reservas WHERE idCliente = %d
  - [ ] Visualização de quanto tempo falta para a próxima reserva
- [ ] Conta
  - [ ] Poder requisitar criação de palavra passe para poder utilizar conta no site caso se tenha registado no local sem dar email
        Ao registar no local, se der um e-mail, irá receber um email que lhe permite atribuir uma palavra passe, ou ao registar se tiver ja registado vai receber o email etc.., ou ao registar se tiver ja registado vai receber o email etc..
  - [ ] Atualizar informações da conta
        UPDATE Cliente SET ... WHERE id=%d
  - [ ] Apagar conta
        DELETE From CLIENTE WHERE id=%d ON DELETE CASCADE (no cliente)

### Cliente workflow

Um cliente pode criar uma conta e efetuar uma reserva

### DB UML

![](./hotelUML.png)
