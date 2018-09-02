# APPLIANCE BD

<p align="justify">Para que o aluno possa configurar o ambiente proposto no presente documento o mesmo deve possuir um computador com no mínimo Processador <b>Quadcore</b> e Memória RAM de <b>3 Giga</b>.
Realizar o download do VirtualBox e do Appliance conforme links descritos a seguir:</p>

[VirtualBox](https://download.virtualbox.org/virtualbox/5.2.18/VirtualBox-5.2.18-124319-Win.exe)

[Appliance](https://drive.google.com/open?id=1MBL2W4konWRzp5O_epwsVXXgEpgfQ6Yd)

<p align="justify">O Appliance é um arquivo que vem empacotado máquinas virtuais prontas para uso, em nosso laboratório existem duas, o srv-mysql e o cliente-mysql.</p>

<p align="justify">Após concluir o download do Appliance, execute o arquivo, e será aberto uma janela do VirtualBox, aceite as opções defaults e aguarde a conclusão da importação das duas máquinas virtuais para seu ambiente.</p>

## DIAGRAMA DE REDE

<p align="justify">Todo o ambiente prático realizado em sala de aula será baseado no ambiente virtual criado pelo VirtualBox, onde é utilizado o sistema operacional <b>Debian 9.5.0</b> em ambas as máquinas virtuais, conforme diagrama descrito na Figura 1.</p>

<p align="center"><img src="images/appliance/01 - diagrama-rede.png"  width="478" height="469" align="middle"/></p>
<h4 align="middle">Figura 01 - Diagrama Rede</h4>

<p align="justify">Com o objetivo de deixar o host <b>cliente-mysql</b> acessando a internet foi criado um pequeno script no srv-mysql para compartilhamento da conexão da interface enp0s8.</p>


## ADMINISTRAÇÃO DOS SISTEMAS

<p align="justify">O Servidor de <b>Banco de Dados</b> não possui ambiente gráfico instalado e já vem com dois usuários previamente criados o <b>root</b> (administrador do sistema) e o usuário <b>aluno</b>, ambos possuem a senha <b>123456</b>.



<p align="justify">O host <b>cliente-mysql</b> vem configurado com um ambiente gráfico mais leve chamado LXDE, o mesmo está configurado para receber ip automaticamente do firewall, o usuário para autenticação no ambiente gráfico é <b>aluno</b> e senha <b>123456</b>, a senha do usuário root também é <b>123456</b>.
É importante pontuar que para o cliente-mysql navegar na internet se faz necessário que o srv-mysql seja inicializado previamente.</p>

## ACESSANDO O MYSQL

<p align="justify">A administração do banco MySql em nosso ambiente será realizado pelo software Workbench, para isso abra o aplicativo, Figura 02, e inicialize uma nova conexão clicando no botão <b>+</b> ao lado de <b>MySQL Connections</b>.</p>
<p align="center"><img src="images/appliance/02 - workbench.png"  width="900" height="626" align="middle"/></p>
<h4 align="middle">Figura 02 - Workbench</h4>
<p align="justify">Atribua um nome para a nova conexão em <b>Connection Name</b>, infome o endereço IP do servidor que está instalado o banco MySql, em nosso caso é o 192.168.0.1 no campo <b>hostname</b>, informe ainda no campo <b>Username</b> o usuário com privilégios de acesso ao banco, já criei previamento um usuário <b>aluno</b> com a senha: 123456, conforme Figura 03.</p>
<p align="center"><img src="images/appliance/03 - workbench-connection.png"  width="850" height="530" align="middle"/></p>
<h4 align="middle">Figura 03 - Configuração Conexão Mysql</h4>
<p align="justify">Em seguida você conseguirar acessar o banco clicando duas vezes na conexão nova que vocês acabaram de criar, conseguindo administrar totalmente o banco de dados. </p>

<p align="justify">Bons Estudos a Todos</p>
<p align="justify">"A mente que se abre para uma nova ideia, jamais voltará para o seu tamanho original"
</p>
Albert Einstein

