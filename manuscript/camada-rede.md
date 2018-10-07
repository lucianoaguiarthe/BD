# <p align="middle"> LABORATÓRIO CAMADA DE REDES</p>

<h2 align="middle">Introdução</h2>
<p align="justify">A Camada de Rede foca na interconexão de enlaces e redes distintas, e para resolver este problemas, são necessários dois personagens: Os protocolos de roteamento e os dispositivos de interconexão de enlaces (switchs ou roteadores)</p>

<h2 align="middle">Sistemas Autônomos</h2>
<p align="justify">Sistemas Autônomos (SA) são agrupamentos de roteadores administrados por um roteador central, geralmente o que está executando o protocolo BGP, conforme Figura 01, podemos observar um grupo de 3 (três) Sistemas Autônomos.</p>
<p align="justify">A Estrutura da Internet feita em Sistemas Autônomos dimimuita a quantidade de tabelas de roteamento replicadas, considerando que as informações inerentes as rotas interna a um SA reservam-se aos seus roteadores de borda.</P>
<p align="center"><img src="images/roteamento/01-as.png"  width="750" height="375" align="middle"/></p>
<h4 align="middle">Figura 01 - Sistemas Autônomos</h4>
<h2 align="middle">Roteamento Estático</h2>
<p align="justify">O roteamento dinâmico interconecta redes distintas, todavia, sua configuração é realizada pelo administrador do ambiente, devendo criar as rotas necessárias em cada roteador da rede, caso ocorra alguma queda do enlace os pacotes continuaram sendo encaminhados para o enlace descontinuada, somente depois da intervenção do administrador criando uma nova rota é que o problema será solucionado.</p>

<h2 align="middle">Roteamento Dinâmico</h2>
<p align="justify">O Roteamento Dinâmico as tabelas são criadas automáticamente pelo algoritmo de roteamento, sem intervenção do administrador do ambiente, devendo a este informar somente qual protocolo de roteamento deve-se utilizar. Os protocolos de roteamento dinâmicos utilizados na camada de rede são:</p>
*  <b>RIP</b> – Utilizada como característica para escolha da rota o caminho mais curto, baseado na quantidade de saltos, é um protocolo interno ao Sistema Autônomo;<p>
* <b>OSPF</b> – Tem como caracterísitca para escolha da rota o estado do enlace, que nem sempre é o caminho mais curto é um protocolo interno ao Sistema Autônomo;<p>
* <b>BGP</b> -  Protocolo de Borda que Interconecta Sistemas Autônomos;<p>

<h2 align="middle">Laboratório Roteamento Dinâmico</h2>

<p align="justify">Iremos realizar a interconexão de duas redes distintas, Figura 2, usando um protocolo de roteamento dinâmico RIP, que utiliza o algoritmo de Vetor de Distância, ou seja, o melhor caminho é o que possui a menor quantidade de saltos</b></p>

<p align="center"><img src="images/roteamento/02-diagrama_rede.png"  width="600" height="391" align="middle"/></p>
<h4 align="middle">Figura 02 - Diagrama Rede</h4>

<h3 align="middle">Entendo a Arquitetura de um Roteador</h3>

<p align="justify">Um roteador é um compador com função específica de interconectar redes, seu hardware funciona de uma maneira um pouco difererente de um computador pessoal, um dos principais fabricantes do mercado é a CISCO, no qual nosso laboratório estará orientado, a Figura 03, apresenta a arquitetura dos componentes principais de um roteador. </p>
<p align="center"><img src="images/roteamento/03-roteador.png"  width="500" height="300" align="middle"/></p>
<h4 align="middle">Figura 03 - Componentes Roteador</h4>

*  <b>RAM</b> – Armazena as tabelas de roteamento e o arquivo de configuração temporário do roteador;<p>
* <b>NVRAM</b> – Armazena o arquivo de configuração que será utilizado na inicialização (startup config), não ocorre perca das informações armazenadas na NVRAM ao desligar o roteador;<p>
* <b>FLASH</b> - Armazena a imagem de inicialização do Sistema Operacional, possui a possibilidade armazenar várias imagens, retém seu conteúdo quando o roteador é desligado;<p>
* <b>ROM</b> -  Mantém instruções que definem o autoteste realizado na inicialização do roteador;<p>
* <b>Console</b> -  É uma interface de acesso direto ao roteador para sua manutenção e atualização de firmware em caso de percado de acesso externo;<p>
* <b>Interfaces</b> -  Conectam o roteador à rede para entrada e saída de pacotes, podem estar diretamenta conectadas na placa-mãe ou adicinadas através de módulos, em computadores pessoas são chamadas de placas de rede;<p>

<p align="center"><img src="images/roteamento/04-aviso-importante.png"  width="300" height="130" align="middle"/></p>
<p align="justify">Todas as configurações realizadas em um roteador são salvas na RAM, portanto é um dado volátil, ocorrendo o desligamento inesperado a configuração feita é <b>PERDIDA</b>, daí a necessidade de salvar constante o que foi realizado na NVRAM através do comando: <i>copy running-config startup-config</i>. </p>

<h3 align="middle">Preparando o Ambiente para Realizar o Laboratório</h3>

<p align="justify">Iremos utilizar um software de simualação de rede desenvolvido e disponibilizado pela própria CISCO, chamado Packet Tracer, ele pode ser executado até mesmo em computadores antigos de 32 bits, para fazer o download cadastre-se no curso:</p>


[Introduction to Packet Tracer](https://www.microsoft.com/pt-BR/download/details.aspx?id=45520)

<p align="justify">É um curso gratuíto de 10 horas, que não tem obrigatoriedade de sua realização, mas já disponibiliza conteúdo e a o download da ferramenta. O mais importante é que você pode até achar o arquivo de instalação do Packet Tracer na internert, todavia para liberar todas as funcionalidades da ferramenta é necessário um login criado no cadastro deste curso, vou disponiblizar a seguir o arquivo para download direto que salvei no google drive:</p>

[Packet Tracer - 32 bits](https://drive.google.com/open?id=10PJHweyAjtvTW5J4JWVAGVdsNSeJKk9f)

[Packet Tracer - 64 bits](https://drive.google.com/open?id=1v3oJeTjKZX5XFH3iwGnDYITVQ1u1FQG_)

[Packet Tracer - Linux](https://drive.google.com/open?id=10dGsuiEm2PqPYw1F5qqx2Pkdquy4sOBQ)

<p align="justify">Após o download faça a instalação do aplicativo que é muito simples, realize o login no mesmo, é o usuário que você cadastrou para ter acesso ao curso, e faça o download do arquivo do laboratório disponiblizado abaixo:</p>

[Laboratório - Roteamento Dinâmico RIP](https://drive.google.com/open?id=1H6cVuwK_GAYC0BXm2RTWAelJVvFJ1O6D)

<h3 align="middle">Execução do Laboratório</h3>
<p align="justify">Ao abrir o arquivo baixado no link acima, o Packet Tracer será aberto com duas telas, uma com o wizard que apresentará seus acerto no final e a outra com o diagrama de rede no qual você irá configurar, Figura4. </p>
<p align="center"><img src="images/roteamento/05-lab-packettracer.png"  width="900" height="448" align="middle"/></p>
<h4 align="middle">Figura 04 - Laboratório Packet Tracer</h4>



<p></P>
Router>enableRouter#configure terminalEnter configuration commands, one per line.  End with CNTL/Z.Router(config)#interface gigabitethernet 0/0Router(config-if)#ip address 192.168.0.1 255.255.255.0Router(config-if)#no shutdownRouter(config-if)#%LINK-5-CHANGED: Interface GigabitEthernet0/0, changed state to up%LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/0, changed state to upRouter(config-if)#exitRouter(config)#interface serial 0/3/0Router(config-if)#ip address 192.168.10.1 255.255.255.0Router(config-if)#no shutdown%LINK-5-CHANGED: Interface Serial0/3/0, changed state to downRouter(config-if)#exitRouter(config)#router ripRouter(config-router)#network 192.168.0.1Router(config-router)#network 192.168.10.1Router(config-router)#passive-interface giGabitethernet 0/0Router(config-router)#endRouter#%SYS-5-CONFIG_I: Configured from console by consoleRouter#copy run startDestination filename [startup-config]? Building configuration...[OK]
Router#]<p align="justify">É importante pontuar que a memória reservada para as máquinas virtuais foram de 1255 MB, todavia podendo diminuir este tamanho, conforme configuração da máquina que estará executando o Appliance. Podemos observar a alocação de memória desejada na Fig. 02.</p>

<p align="center"><img src="images/samba/02_virtualbox.png"  width="800" height="493" align="middle"/></p>
<h4 align="middle">Figura 02 - Alocação de Memória VM</h4>


## INSTALAÇÃO SAMBA

<p align="justify">Para instalação do Samba devemos baixar os pacotes: samba, kerbero, smbcliente e winbind, conforme comando a seguir:</p>

**<h4 align="middle">apt-get install samba krb5-config winbind smbclient</h4>**

<p align="justify">Ao final da instalação são solicitadas informações sobre configuração do kerbero. A primeira tela Fig. 03, solicita qual o nome do domínio, o qual configuraremos <b>aluno.com.br</b>.</p>

![](images/samba/07_kerberos.png)
<h4 align="middle">Figura 03 - Realm Kerberos</h4>


<p align="justify">Será solicitado também o IP do servidor responsável pelo domínio. Iremos configurar o endereço loopback, já que o kerberos está sendo executado no mesmo host do samba:</p>

<p align="center"><img src="images/samba/08_kerberos.png"  width="700" height="205" align="middle"/></p>
<h4 align="middle">Figura 04 - Servidor Kerberos</h4>

<p align="justify">E ainda é solictado o ip do servidor administrativo que também será o endereço loopback, conforme explicações anteriores:</p>

<p align="center"><img src="images/samba/09_kerberos.png"  width="700" height="205" align="middle"/></p>
<h4 align="middle">Figura 05 - Servidor Administrativo</h4>

<p align="justify">Ao concluir a instalação devemos renomear o arquivo principal de configuração do samba o <b>smb.conf</b>, para que ao aprovisionar o domínio, seja gerado um novo smb.conf, de acordo com o comando a seguir:</p>

<h4 align="middle">mv /etc/samba/smb.conf /etc/samba/smb.conf.original</h4>

<p align="justify">O passo seguinte deveremos configurar o samba como controlador de domínio, é importante pontuar que o nome do nosso domínio será <b>aluno.com.br</b> e o nome da máquina q está executando o samba é <b>samba-dc</b>, através do comando <b>samba-tool</b> conforme apesentado na Fig. 06:</p>
<p style="text-align: justify;"><b>IMPORTANTE: A senha cadastrada deve possuir um nível alto de complexidade, use número, letras e símbolos, caso coloque uma senha simples dará um erro no final da instalação</b></p>

![](images/samba/10_domain_provision.png)
<h4 align="middle">Figura 06 - Comando samba-tool</h4>

<p align="justify">Onde você informará qual realm do domínio, em nosso exemplo <b>aluno.com.br</b>, qual o domain, o modo como o serviço samba está operando, se <b>DC</b> como controlador de domínio ou <b>standalone</b> somente para compartilhamento de arquivos, qual tipo de dns estará fazendo a resolução de nomes, em nosso exemplo estaremos utilizando o do próprio samba <b>SAMBA_INTERNAL</b> e qual endereço do dns estará redirecionando as solicitações de resolução de nome. Responda todas estas perguntas conforme Fig. 06.</p>

<p align="justify">Ao concluir a configuração será gerado um novo smb.conf bem como o arquivo de configuração do kerberos e apresetnado um relatório conforme Fig. 07:</p>

![](images/samba/11_domain_provision.png)
<h4 align="middle">Figura 07 - domain_provision</h4>

<p align="justify">O arquivo smb.conf gerado no comando <b>samba-tool domain provision</b> é apresentado na Fig. 08 e corresponde a configuração inicial do samba:</p>

<p align="center"><img src="images/samba/12_smb.conf.png"  width="700" height="307" align="middle"/></p>

<h4 align="middle">Figura 08 - Arquivo smb.conf</h4>

<p align="justify">Ao concluir  toda a  configuração  podemos  fazer um teste no samba utilizando o  smbcliente, conforme apresentado na Fig. 09</p>

<img src="images/samba/13_teste_samba.png"  width="700" height="278" align="middle"/>
<h4 align="middle">Figura 09 - Teste Samba</h4>

<p align="justify">Faz-se necessário copiar o arquivo gerado pelo kerberos durante o aprovisionamento do domínio para a pasta <b>etc</b>:</p>
<h4 align="middle">mv /var/lib/samba/private/krb5.conf /etc/</h4>

<p align="justify">O administrador do sistema deverá derrubar todos os serviços do samba, objetivando alterar configurações, conforme comando abaixo:</p>
<h4 align="middle">systemctl stop smbd.service nmbd.service winbind.service </h4>

<p align="justify">Devemos desativar todos os serviços do samba para não serem iniciados no boot, impossibilitando o AD de subir:</p>

<h4 align="middle">systemctl disable smbd.service nmbd.service winbind.service</h4>

<p align="justify">O serviço samba-ad-dc ao ser instalado ele vem mascarado, desta forma o mesmo é impedido de ser iniciado ou parado, para que possamos parar ou iniciar o serviço manualmente devemos desmascarar o samba com o comando:</p>

<h4 align="middle">systemctl unmask samba-ad-dc.service</h4>

<p align="justify">Como o samba-dc-ad foi parado anteriormente, devemos inicializá-lo:</p>

<h4 align="middle">systemctl start samba-ad-dc.service </h4>

<p align="justify">Habilite com o comando abaixo o serviço samba-ad-dc para inicializar no boot:</p>

<h4 align="middle"><b>systemctl enable samba-ad-dc.service</b></h4>

<p align="justify">Podemos ainda tirar a complexidade da senha usando o samba-tool, conforme apresentado na Fig. 10:</p>

![](images/samba/14_complexity_samba.png)
<h4 align="middle">Figura 10 - Alteração Complexidade de Senha</h4>

<p align="justify">Caso o administrador de rede deseje, pode especificar o tamanho mínimo de uma senha, na Fig. 11, configuramos que o usuário tenha uma senha como no mínimo 6 caracteres ou símbolos</p>

![](images/samba/15_password_length.png)
<h4 align="middle">Figura 11 - Tamanho da Senha</h4>

## CONFIGURAÇÃO DO RSAT

<p align="justify">O serviço samba pode ser administrado diretamente no host em que está instalado o serviço, ou podemos administrá-lo remotamente por meio do software RSAT instalado em um computador com sistema operacional Windows que esteja previamente autenticado no domínio. Você verá que a configuração passa a ser igual a do Windows Server. Em nosso diagrama (Fig. 01), iremos administrar o samba a partir do host RSAT-PC, que tem o IP 192.168.5.10.</p>
<p style="text-align: justify;">

<p align="justify">Segue abaixo endereços para instalação do RSAT nas diversas versões de Windows, no nosso laboratório já realizei o download prévio:</p>

### DOWNLOAD

[Windows 10](https://www.microsoft.com/pt-BR/download/details.aspx?id=45520)<p>
[Windows 8.1](https://www.microsoft.com/pt-BR/download/details.aspx?id=39296)<p>
[Windows 8](https://www.microsoft.com/pt-BR/download/details.aspx?id=28972)<p>
[Windows 7](https://www.microsoft.com/pt-BR/download/details.aspx?id=7887)

<p align="justify">Antes de instalar o <b>RSAT</b> devemos ingressar o host no domínio. Acesse o painel de controle e vá em sistemas em segurança => sistemas, será exibido uma janela conforme Fig. 12:</p>

<p align="center"><img src="images/samba/16_rsat_domain.png"  width="700" height="542" align="middle"/></p>
<h4 align="middle">Figura 12 - Sistemas</h4>

<p align="justify">Na área de configurações de grupo de trabalho clique em alterar configurações, no qual será exibido a janela de propriedades do sistemas (Fig. 13). Clique no botão <b>Alterar</b> para informar o domínio que devemos ingressar.</p>

<p align="center"><img src="images/samba/17_rsat_domain.png"  width="400" height="469" align="middle"/></p>
<h4 align="middle">Figura 13 - Propiedades do Sistemas</h4>

<p align="justify">Na janela de alterações do domínio (Fig. 14), você terá a posibilidade de alterar o domínio e o nome do computador. Marque o item domínio e coloqueo o nome <b>aluno</b>.</p>

<p align="center"><img src="images/samba/18_rsat_domain.png"  width="400" height="469" align="middle"/></p>
<h4 align="middle">Figura 14 - Alteração de Domínio</h4>

<p align="justify">Ao alterarmos o domínio, será solicitado um usuário e senha para ingressar no domínio. O usuário é o <b>Administrator</b> e a senha é a cadastrada quando foi aprovisionado o domínio (Fig. 15).</p>

<p align="center"><img src="images/samba/19_rsat_domain.png"  width="380" height="269" align="middle"/></p>
<h4 align="middle">Figura 15 - Senha Domínio</h4>

<p align="justify">Se a configuração feita no samba estiver toda correta, será apresentada uma janela de confirmação, dando boas vindas ao domínio, Fig. 16.</p>

<p align="center"><img src="images/samba/20_rsat_domain.png"  width="700" height="388" align="middle"/></p>
<h4 align="middle">Figura 16 - Confirmação Domínio</h4>

<p align="justify">Conforme abordado anteriormente, deve-se instalar o RSAT somente depois que o host fizer parte do domínio, no Appliance disponilizado, o instalador do RSAT está localizado em <b>c:\samba</b>, Fig. 17. Faça a instação do mesmo.</p>

![](images/samba/21_folder_rsat.png)
<h4 align="middle">Figura 17 - Diretório Instalador RSAT</h4>

<p align="justify">Ao concluir a instalação, será criado um item no menu iniciar <b>Ferramentas Administrativa</b> (Fig. 18), que possuirá várias ferrametas para administração do domínio.</p> 

![](images/samba/22_user_pc_ad.png)
<h4 align="middle">Figura 18 - Ferramentas Administrativas</h4>

<p align="justify">A primeira configuração a ser relizada é referente aos usuários. Selecione o item Usuários e Computadores do Active Directory, no qual abrirá uma janela para administração de usuário e unidades organizacionais (Fig. 19).</p>

<p align="justify">As Unidades Organizacionais-OU são contêineres que armazenam informações sobre usuários e computadores. Em nosso exemplo iremos criar uma OU para armazenar nossos novos usuários a serem criados. Para isso clique com o botão direito em cima do nome do domínio, selecione no menu suspenso o item Novo => Unidade organizacional.</p>

![](images/samba/23_create_ou.png)
<h4 align="middle">Figura 19 - Usuários e Computadores do AD</h4>

<p align="justify">Vamos criar uma Unidade Organizacional chamada nassau, desmarque a opção proteger contêiner, conforme Fig. 20:</p>

<p align="center"><img src="images/samba/24_create_ou.png"  width="450" height="384" align="middle"/></p>
<h4 align="middle">Figura 20 - Unidade Organizacional</h4>

<p align="justify">Para cadastrar um usuário no domínio devemos clicar com o botão direito em cima da Unidade Organizacional nassau e no menu suspenso selecionar Novo => Usuário.</p>

![](images/samba/25_create_user.png)
<h4 align="middle">Figura 21 - Menu Usuário</h4>

<p align="justify">Na janela de cadastro do usário, preencha os campos de nome e usuário, conforme Fig. 22. Para cadastrar um usuário no domínio, devemos clicar com o botão direito em cima da Unidade Organizacional nassau e no menu suspenso selecionar Novo => Usuário.</p>

<p align="center"><img src="images/samba/26_create_user.png"  width="450" height="383" align="middle"/>
<img src="images/samba/27_create_user.png"  width="450" height="386" align="middle"/></p>
<h4 align="middle">Figura 22 - Cadastro Usuário</h4>

<p align="justify">Com o objetivo de implementar algumas restrições no sistema operacional dos usuários, devemos criar as Group Police-GPO, as mesmas possuem diversas implementações para personalização dos sistemas operacionais que fazem parte do domínio, como restrição ao painel de controle e configuração de rede. É importante pontuar que tal configuração é idêntica no Windows Server, todavia a possibilidade desta implementação no samba só veio a partir da versão 4.</p>

<p align="justify">Para configurarmos uma GPO devemos acessar o menu de Ferramentas Administrativas e Gerenciamento de Políticas de Grupo (Fig. 23):</p>

![](images/samba/28_gpo.png)
<h4 align="middle">Figura 23 - Cadastro Usuário</h4>

<p align="justify">Na criação da GPO devemos escolher o domínio (aluno.com.br), clicar com o botão direito em cima da OU nassau e no menu suspenso selecionar criar uma GPO neste domínio e atribur um nome para ela (Fig. 24).</p>

![](images/samba/29_create_gpo.png)
<h4 align="middle">Figura 24 - Criação GPO</h4>

<p align="justify">Devemos editar a GPO criada, clicando com o botão direito em cima dela e nome menu suspenso selecionar a opção Editar, Fig. 25.</p>

![](images/samba/30_edit_gpo.png)
<h4 align="middle">Figura 25 - Edição GPO</h4>

<p align="justify">Iremos implementar uma restrição para os usuários da OU nassau, no qual os mesmos serão impossibilitados de realizar alterações na configuração avançada TCP/IP. Para isso, selecione configuração do usuário => Modelos Administrativos => Rede => Conexões de Rede e edite a opção do lado direito da janela <b>Proibir a configuração avançada do TCP/IP</b>, selecione opção habilitado, conforme Fig. 26:</p>

![](images/samba/31_edit_gpo_lan.png)
<h4 align="middle">Figura 26 - GPO Configuração de Rede</h4>

<p align="justify">Ainda como exemplo, iremos ocultar a opção Adicionar ou Remover pogramas do Painel de Controle dos usuários da OU nassau. Para isso selecione configuração do usuário =>Adicionar ou Remover Programas e edite a opção do lado direito da janela <b>Remover opção Adicionar/Remover Programas</b>, selecione opção habilitado (Fig. 27).</p>

![](images/samba/33_edit_gpo_programas.png)
<h4 align="middle">Figura 27 - GPO Painel de Controle</h4>

## CONFIGURAÇÃO DO CLIENTE

<p align="justify">Para testarmos a configuração do usuário, iremos utilizar o host Cliente-PC (Fig. 01). Devemos ingressar o mesmo no domínio, conforme abordado anteriormente, e logar com o usuário <b>pedro</b>.</p>

<p align="justify">Ao tentarmos acessar as configurações de rede será apresentado uma tela de autenticação (Fig. 28). Considerando que o usuário <b>pedro</b> não tem permissão de acesso a estas configurações de rede</p>

<p align="center"><img src="images/samba/36_client_edit_lan.png"  width="300" height="258" align="middle"/></p>
<h4 align="middle">Figura 28 - Configurações de Rede</h4>


<p align="justify">Ao abrirmos o painel de controle, em adicionar ou remover programas, podemos observar que não existe opção para remover nenhum programa do sistema operacional, conforme mostra a Fig. 29.</p>

<p align="center"><img align="middle" src="images/samba/37_client_edit_software.png"  width="700" height="525"/></p>
<h4 align="middle">Figura 29 - Painel de Controle</h4>

