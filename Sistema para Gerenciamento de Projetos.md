#Sistema para Gerenciamento de Projetos

-Funcionalidades: 

	- O sistema tem como objetivo adicionar, organizar e editar diversos tipos de projetos.
	- Permite a consulta do total de projetos, de usuários e de atividades no sistema.
	- Métodos:
		- EditarStatus(ArrayList<Projetos>,int indicedoprojeto,Usuario coordenador)(Status/Interface): Permite o coordenador associado editar o status de algum projeto em questão se o projeto atender os requisitos minimos para alteração.

		- associarProjetos(Projetos projetoatual, Usuario usuarioatual)(Usuarios): Associação de Projetos ao ArrayList do Usuario desejado.

		- associarAtividadesemUsuario(Usuarios usuarioatual,Atividades atividadeatual)(Usuarios): Associação de Atividades ao ArrayList do Usuario desejado.

		- associarAtividadesemProjeto(Projetos projetoatual,Atividade atividadeatual)(Projetos): Associação de Atividades ao ArrayList do Projeto desejado.

		- adicionartarefas(Usuarios profissionalatual,String tarefa)(Profissionais): Adicionar tarefas relacionadas as atividades do Profissional desejado. 

		- add(ArrayList<Usuarios>,String nome,String email,String tipodeusuario)(Usuario): Adiciona Usuarios ao sistema.

		- add(ArrayList<Atividades>,String identificacaoa, String descricaoa,String datadeinicioa,String horadeinicioa,String datadeterminoa,String horadeterminoa, Usuario responsavel)(Atividades): Adiciona Atividades ao sistema.

		- add(ArrayList<Projetos>,String identificacao,String descricao,String datadeinicio,String horadeinicio,String datadetermino,String horadetermino,String tipodeProjeto, Usuario coordenador(Projetos): Adiciona Projetos ao sistema.

		- remover(ArrayList<Usuarios>, int indicedousuario)(Usuarios): Remove Usuarios do sistema.

		- remover(ArrayList<Atividades>,int indicedaatividade)(Atividades): Remove Atividades do sistema.

		- remover(ArrayList<Projetos>, int indicedeprojetos)(Projetos): Remove Projetos do sistema.

-Classes:
1 - SistemaPrincipal:

		- Motivação: Principais funcionalidades de adição e edição dos projetos.

		- Solução: Acesso as partes referentes a adição e edição para o usuário utilizando o sistema.

		- Vantagens: Melhor entendimento das funcionalidades do código em relação as especificações do usuário utilizando o sistema.  
                                  
		- Desvantagens:	Essa classe em especifico terá um método bastante extenso.

2 - Projetos:

		- Motivação: Classe com as principais funcionalidades dos Projetos que serão gerenciados.

		- Solução: Instaciar os Projetos já que essa classe contém as variáveis necessárias aos projetos.

		- Vantagens: Organização, já que somente a acessando podem-se fazer as associações.

3 - Atividades:

		- Motivação: Classe com as principais funcionalidades das Atividades que serão gerenciadas.

		- Solução: Instaciar as Atividades já que essa classe contém as variáveis necessárias aos projetos.

		- Vantagens: Organização, já que somente a acessando podem-se fazer as associações.

-Distribuição de Métodos:

	- EditarStatus(Status/Interface): Está presente nas classes que implementam a interface.

	- associarProjetos: Presente na classe Usarios já que a mesma irá fazer as alterações de usuarios.

	- associarAtividadesemUsuario: Presente na classe Usuarios já que a mesma irá fazer as alterações de usuarios.

	- associarAtividadesemProjeto: Presente na classe Projetos já que a mesma irá fazer as alterações de projetos.

	- adicionartarefas(Profissionais): Presente na classe Profissionais por associação.

	- add(Usuario): Presente na classe Usuarios porque esse método fará a adição de Usuarios ao sistema.

	- add(Atividades): Presente na classe Atividades porque esse método fará a adição de Atividades ao sistema.

	- add(Projetos): Presente na classe Projetos porque esse método fará a adição de Projetos ao sistema.

	- remover(Usuarios): Presente na classe Usuarios já que a mesma irá fazer as alterações de projetos.

	- remover(Atividades): Presente na classe Atividades já que a mesma irá fazer as alterações de projetos.

	- remover(Projetos): Presente na classe Projetos já que a mesma irá fazer as alterações de projetos.

		- Motivação: Organizar o sistema de modo em que a funcionalidade do método tenha a maior relação possivel com a classe que está presente.

		- Solução: Coloca os métodos necessários em suas respectivas classes associadas.

		- Vantagens: Praticidade na busca de certos métodos.

		- Desvantagens: Algumas classes podem até ficar muito extensas.

-Herança:

	Subclasses:
	- Alunos: Particularmente será necessário informar o tipo do aluno para o associar ao projeto, então foi criada essa classe para esse atributo diferencial.

	- Professores: é visto que os professores como coordenadores de projeto precisariam ser diferenciados dos demais usuários e ainda assim ter seus atributos em comum, logo a herança possibilita que seja implementada uma interface a aquela classe sem ter que generalizar essa particularidade a todos os usuário já que não é necessário.

	- Pesquisadores: É semelhante ao caso da classe Professores, os Pesquisadores também poderão ser coordenadores de projeto e assim modificar seu status, por isso foi necessária a herança.
	- Tecnicos: Tem como diferencial sua especialidade.

	- Profissionais: Necessária para tanto os tipos de profissionais quanto as tarefas associadas a eles.

		- Motivação: Foi necessário o uso de herança apresentado nessa parte do sistema para que se dividam melhores os tipos de usuários com os demais, como por exemplo, na criação de atributos diferenciais entre essas classes.

		- Solução: Assim, não foram utilizados atributos desnecessários para outros tipos.

		- Vantagens: Manipulação em relação a adição, já que como é uma extensão ela permite adicionar mais informações referentes somente a aquele grupo seleto.

		- Desvantagens: Se considerarmos que um dia pode haver uma adição de tipo de Usuarios ao sistema, ou até mesmo um atributo diferenciado, seria mais interessante fazer uma nova subclasse. Também a manipulação em relação ao acesso a alguns atributos diferenciados.

-Classe Abstrata:

	- O sistema possui uma classe abstrata (Usuarios).

		- Motivação: Contém atributos relacionados aos diversos tipos de Usuario.

		- Solução: É uma super classe dos tipos de Usuario mas já que não necessariamente é preciso instanciar um objeto do único tipo Usuario mas sim de suas classes relacionadas, logo, os objetos relacionados da classe abstrata Usuarios seria acessada por meio de suas subclasses.

		- Vantagens: Essa classe vai conter os atributos em comum as suas subclasses, assim, é possivel deixar o sistema mais resumido.

		- Desvantagens: Se considerarmos que um dia o usuário quisesse instaciar um Usuario, isso não seria possivel.

-Interface:

	- Implementada na subclasse Professor e na subclasse Pesquisadores.

		- Motivação: A interface será necessária para a aplicar a possibilidade de modificação de status de um projeto somente para classes implementadas.

		- Solução: É utilizada nas classes necesssárias particularmente para o método de modificação de status dos projetos.

		- Vantagens: Já que foram estendidas as funcionalidades com a herança, a utilização de interface é vantajosa para garantir que suas subclasses sigam os mesmos métodos.

		- Desvantagens: Em alguns sistemas pode ser desvantajosa a obrigatoriedade de certos métodos.

-Polimorfismo:

		- Motivação: É utilizada interface no sistema assim o polimorfismo é inevitável para os métodos implementados. 

		- Solução: Na interface são necessárias a utilização de métodos de mesmo nome onde aplicada, gerando assim polimorfismo.


-Tratamento de Exceções:

	As exceções utilizadas são referentes a classes e a possibilidade de acesso a partes não permitidas pelo sistema.

		- Motivação: Tratar erros recorrentes no sistema que podem dar problema em aguns casos.

		- Solução: As exceções utilizadas estão relacionadas a erros em certas situações, tais erros atrapalhavam na execução do programa já que ele poderia parar de executar.

		- Vantagens: O programa continua a executar e o tratamento não atrapalha nesses casos.

		- Desvantagens: O sistema fica mais extenso.


-Extensibilidade:

		-Motivação: Foi visto necessário utilizar essa extensões porque tais classes contêm variáveis que só estão relacionadas a elas no sistema, ou seja, por causa da herança onde uma super classe teve três subclasses.

		-Solução: Foram utilizadas para maior organização do sistema.

		-Vantagens: Organização.

		-Desvantagens: Maior utilização de classes.

-Reuso:

		- Motivação: Foi necessária a utilização de alguns métodos mais de uma vez no código.


